## Test Case 15.17

> End user BCCP state management

Pre-condition: The user is on the BCCP detail page, which he owns.

All these state changes need a confirmation dialog box with slightly different messages.

### Test Assertion:

1. The end user can change the BCCP state from WIP to QA, if he is the owner.
2. The end user can change the BCCP state from QA back to WIP, only if he is the owner.
3. The end user can change the BCCP state from QA to Production, only if he is the owner.

### Test Step Pre-condition:



### Test Step: