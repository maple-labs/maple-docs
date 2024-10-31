# Overview

The RecapitalizationModule contract provides functionalities related to Recapitalization in a protocol. It allows for the claiming of tokens based on predefined issuance windows and manages the scheduling of these windows.

Here is a summary of what the RecapitalizationModule contract does:

1. Claiming Tokens: The contract allows designated Recapitalization claimers to claim tokens based on predefined issuance windows. Claimers can call the `claim` function to claim tokens. The claimable amount is calculated based on the issuance rate specified for each window and the `claim` function is restricted to callers with the `RECAPITALIZATION_CLAIMER` tag in Global's `isInstance` mapping.

2. Viewing Claimable Tokens: The contract provides a function `claimable` that allows anyone to view the amount of tokens that can be claimed up to a specified timestamp. This provides transparency and visibility into the claimable tokens.

3. Managing Issuance Windows: The contract supports the scheduling of issuance windows. The governor, as defined in the associated Globals contract, can schedule new issuance windows by specifying window start timestamps and corresponding issuance rates. These windows determine the issuance rates for the tokens during different periods.

4. Determining Current Issuance Rate: The contract provides a function `currentIssuanceRate` that returns the issuance rate for the current issuance window based on the current timestamp. This allows users to know the current rate at which new tokens are being issued.

## Issuance Windows
The contract maintains a list of `windows`, which each represents a specific time period during which tokens are issued at a predefined rate.
There are 2 main factors that define a window:
**start**: The timestamp that defines when the window becomes valid.
**issuanceRate**: The amount of tokens per seconds that will be issued during that window.
**nextWindowId**: This structure is implemented as a linked list, so each window saves a reference to the next window. If this value is zero, it means that it's the last schedule in the list.

Note that windows don't have a specific end time, so they'll be forever valid until a subsequent window is scheduled.

## Scheduling
It's the act of lining up issuance windows to effectively change the issuance rate of the token. It's only possible to schedule a window with a future start date, including required timelock duration.

To properly schedule a issuance window, the following steps need to be done:
1. `Governor` should call `Globals.scheduleCall(module address, function id, encoded data)`, where:
 * `module address`: The deployed address of the Recapitalization module contract.
 * `function id`:   A bytes 32 indicating which function is being scheduled. In this case it's `"IM:SCHEDULE"`.
 * `encoded data`:  Which can be computed using: `abi.encodeWithSelector(RecapitalizationModule.schedule.selector, uint32[] windowStarts, uint208[]issuanceRates)`

2. After the time lock period passed, the `Governor` should call `module.schedule(uint32[] windowStarts, uin208[]issuanceRates)`.

### Scheduling Parameters
The `schedule()` function takes 2 arrays as parameter, one for the starts of each issuance window, and the other for the issuance rates, represented by the amount of tokens per second.

For example, let's use the proposed distribution for the 3 year period described in the [MIP-009](https://community.maple.finance/t/mip-009-upgrade-mpl-token-design/300)

<img src="https://global.discourse-cdn.com/standard10/uploads/maple/original/1X/4a9a843bada092ceeaa8121bfd54a56402e44986.png" >

Here's how to derive each parameter:

1. Get the timestamps of the desired periods. There's a need to schedule 4 windows so the issuance stops after the third full year. Those values are:
- **1696132800** -> October 1st 00:00 2023 EST
- **1704081600** -> January 1st 00:00 2024 EST
- **1735704000** -> January 1st 00:00 2025 EST
- **1767240000** -> January 1st 00:00 2026 EST

Thess will be be the first parameter to `schedule`.

2. Get the duration, in seconds, of each desired period, except for the last one. Those values are:
- **7948800**  -> 92 days  (October 1st 2023 - December 31st 2023)
- **31622400** -> 366 days (January 1st 2024 - December 31st 2024)
- **31536000** -> 365 days (January 1st 2025 - December 31st 2025)

3. To get the proper issuance rate, just divide the desired number of tokens including decimals, taken from the MIP, by the period duration, from step 2:
- **1st Period**: `125000e18 / 7948800 = 15725644122383252`
- **2025**: `566767e18 / 31622400 = 17922959674155030`
- **2026**: `595641e18 / 31536000 = 18887652207001524`
- **2027**: 0, since the issuance stops after the third year.

The next step is to divide the amount of tokens, by the duration of the period, which would yield the following results:`[15725644122383252, 17922959674155030, 18887652207001524, 0]`

In conclusion, to configure the mentioned issuance schedule, the function to be called is:
```
module.schedule([1696132800, 1704081600, 1735704000, 1767240000],[15725644122383252, 17922959674155030, 18887652207001524, 0])
```

### Insertion Logic
The insertion logic works as follow:
```
The Recapitalization module has a defined schedule of issuance that defines how new tokens will be issued over time.
Here is an example of an issuance schedule with three windows, the first two windows have a defined start and end.
The last window has a defined start but lasts indefinitely after it starts since it is the last window in the schedule.

|--------|------|---------------->
    W1      W2          W3

Each window has a separate issuance rate, which defines how many tokens per second will be issued during it's duration.
The issuance rate generally increases over time and is used to simulate the effect of compounding (for example on a yearly basis).
However the issuance rate can also be zero to indicate that no tokens should be issued.

|----|==============|________|≡≡≡≡≡≡≡≡≡≡≡≡>
  W1        W2          W3         W4

New windows can be scheduled, but only from the current time, retroactive scheduling is not possible.
When new windows are scheduled after the last window in the schedule starts, they will be appended to the schedule.

|--------|----------|----------------->
    W1        W2         ^  W3
                         |
|--------|----------|----|------------>
    W1        W2      W3       W4

When new windows are scheduled before any of the existing windows in the schedule start, they will replace them instead.

|--------|----------|--------------->
    W1        W2 ^         W3
                 |
|--------|-------|------------------>
    W1        W2          W4
```
