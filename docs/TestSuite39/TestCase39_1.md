## Test Case 39.1

> Access to DT viewing, editing and commenting

Pre-condition: A release branch, i.e., one of the release branches, is selected.



### Test Assertion:

1. The developer can see in the CC View/Edit page all DTs owned by any user in any state in the selected release. There should not be any developer DT listed in a release branch that is not in the Published state (this is not a query condition, i.e., such situation shouldn’t exist in the database).
2. The developer CAN view but CANNOT edit the details of a DT in the selected release that is in WIP state and owned by another user. He can also add comments.
3. The developer can view the details of an DT that is in QA and owned by any user, but he cannot make any change except adding comments.
4. The developer can view the details of an DT which is in Production state owned by any user but he cannot make any change. He also cannot make an amendment on the DT either, but he can add comments.
5. The developer can view the details of an DT that is in Deleted, but he cannot make any change except adding comments. He cannot either restore the Deleted DT.
6. The developer can view details of any Published DT but cannot make any change except adding comments.
7. The developer cannot make a new revision on any DT.
8. The developer shall not be able to create any new DT.

### Test Step Pre-condition:



### Test Step: