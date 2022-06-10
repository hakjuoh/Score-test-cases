## Test Case 15.5

> End user ACC state management

Pre-condition: The end user is on the ACC detail page, which he owns.

All these state changes need a confirmation dialog box with slightly different messages. Changing to the QA state only need a confirmation. Retracting a QA ACC to WIP needs a confirmation. Amending a Production ACC which set its state to WIP needs a confirmation.

### Test Assertion:

1. The end user can change the ACC state from WIP to QA. The system shall then change the state of its children associations that are also in the WIP state to the QA state. There is no need to check the state of the dependencies (we will ensure that everything is consistently in the Production state when a BIE Extension that has the end user CC is expanded). (Note that I change the rule about viewing details of CC in WIP state that the detail can be viewed by any user so the user should be able to expand the tree of the ACC).
2. The end user can change the ACC state from QA back to WIP. State of the associations also go back to WIP.
3. The end user can change the ACC state from QA to Production. State of the associations also go to Production.

### Test Step Pre-condition:



### Test Step: