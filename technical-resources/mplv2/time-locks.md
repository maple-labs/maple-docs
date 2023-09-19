# Time locks

To ensure that all stakeholders can take action in case of unwanted events, administrative functions should be time-locked before execution. The following functions will have a time lock:

- Add Module
- Remove Module
- Upgrade

Note that since the modules themselves call the mint function, it does not need to be time-locked. The current protocol already has a similar time-locking mechanism in place, which can be leveraged for MPL V2.
