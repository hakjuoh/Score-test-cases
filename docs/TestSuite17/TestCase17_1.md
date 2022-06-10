## Test Case 17.1

> Code list access

Pre-condition: A release branch is selected.



### Test Assertion:

1. The end user can see in the View/Edit Code List page all code lists (CLs) owned by any end user in any state. Included in the list must also be all developer code lists in Published state. There must not be any code list in Draft, Candidate, or Release Draft state.
2. The end user can view and edit the details and code values of an end user CL that is in WIP state and owned by him.
3. The end user CAN view but CANNOT edit the details of a CL that is in WIP state and owned by another end user. He can however add comments.
4. The end user can view the details of a CL that is in QA or Production state and owned by another end user but he cannot make any change except adding comments.
5. The end user can view details of any developer code list in the selected release branch. The CL must always be in the Published state. He cannot make any change. He can add comments.

### Test Step Pre-condition:



### Test Step: