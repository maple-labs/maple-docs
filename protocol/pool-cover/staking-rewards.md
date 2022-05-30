---
description: These rewards are subject to change.
---

# Pool Cover Returns

Pool Cover will receive one-tenth of the interest yield in a Pool plus MPL rewards.&#x20;

The APY from MPL rewards will vary depending on 1) the volume of MPL provided; and 2) the MPL price.&#x20;

The MPL Rewards implementation will be a single deposit of a fixed number of MPL to the  Rewards Contract at the start of each month.

This will be determined based on:&#x20;

* Average MPL price over preceding 7 days
* Target Cover Volume in the protocol for the next month
* Target all in APY that month and average interest rate on loans in the pool

**Target Cover Volume size**

The Cover Reserve provides additional collateral protection in case of defaults on undercollateralized loans in a Lending Pool. The target reserve size is around 8-12% of the balance of loans in a pool. The MPL rewards would be sized to hit the target all-in APY if actual cover volume meets the target reserve size. E.g. if a Pool has $100M of loans, then $8M-$12M cover reserve. \


**Target all-in APY**

The target all in APY is calculated as this USDC fee plus MPL rewards. Current market conditions for stablecoin farming are generally 15-20% APY. The Cover Reserve receives 0.1x the interest yield in the Pool as fees.&#x20;

* If the average interest rate on loans in the pool is 10%, then 1% (i.e. 0.1\*10%) goes to the reserve as fees.&#x20;
* If the Cover Reserve is 10% of the loans outstanding, then USDC fee APY is 10% (i.e. 1% / 10%).&#x20;
* Thus to achieve the target all-in APY of 15-20%, the target MPL rewards would be 5%-10% and the number of MPL deposited at the start of the month would be set accordingly.

[Calculated example can be found here](https://docs.google.com/spreadsheets/d/1z1uGemb9gEPVavwLF11N\_g6iUyrUG7lXgRRhEzHgSkc/edit?usp=sharing)****\
****
