## Test Case 37.1

> Agency ID access

Pre-condition: A release branch is selected.

### Test Assertion:

#### Test Assertion #1
The end user can see in the View/Edit Agency ID List page all Agency ID lists owned by any end user in any state. There must also be all developer Agency Id lists in Published state. There must not be any Agency ID list in Draft, Candidate, or Release Draft state.

#### Test Assertion #2
The end user can view and edit the details and Agency ID List values of an end user Agency ID list that is in WIP state and owned by him.

#### Test Assertion #3
The end user CAN view but CANNOT edit the details of an Agency ID list that is in WIP state and owned by another end user. He can however add comments.

#### Test Assertion #4
The end user can view the details of an Agency ID list that is in QA or Production state and owned by another end user but he cannot make any change except adding comments.

#### Test Assertion #5
The end user can view details of any developer Agency ID list in the selected release branch. The Agency ID list must always be in the Published state. He cannot make any change. He can add comments.

#### Test Assertion #6
Developer users CAN view but CANNOT edit end user’s agency ID lists in any state.

### Test Step Pre-condition:



### Test Step: