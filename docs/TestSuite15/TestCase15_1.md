## Test Case 15.1

> Access to core component viewing, editing, and commenting

Pre-condition: N/A



### Test Assertion:

1. The end user can see in the CC page all CCs owned by any user in any state. But there shall not be any developer CC listed in a release branch that is not in the Published state (this is not a query condition, i.e., such situation shouldn’t exist in the database). UEGACC if exists in that branch shall be listed while UEGASCC and UEGASCCP shall NOT be listed.
2. The end user can view and edit the details of a CC that is in WIP state and owned by him. He can also change state of the CC to QA state.
3. The end user can view the detail of a CC that is in QA state owned by him. He cannot edit the detail. He can only add comments or change the state to Production.
4. The end user can view the detail of a CC that is in Production state owned by him. He cannot edit the detail. He can only add comments or amend the CC.
5. The end user CAN view but CANNOT edit the details of a CC that is in WIP state and owned by another user (in principle, only end user CCs can be in the WIP state in a release branch), and he CAN add comments.
6. The end user can view the details of a CC that is in QA state and owned by another user but he cannot make any change except adding comments (in principle, only end user CCs can be in the QA state in a release branch).
7. The end user can view the details of a Production CC owned by another user but he cannot make any change except adding comments. The end user can also amend the CC, in which case, he takes over the ownership.
8. The end user can see the detail of developer CCs but cannot make any change. He can only make comments.
9. The end user can move the state of multiple CCs at once.
10. The end user can open a CC and find the usages of its nodes (i.e., ACC, ASCCP or BCCP) by invoking the function “Where Used” of the context menu of a particular node. In the returned dialog, he can view where the CC wherein the selected CC is used. Check the usages for ACC, ASCCP and BCCP nodes.
	1. If an ACC is selected to view wherein it is used, then the ACCs which are based on this ACC either directly or indirectly should be listed in the returned dialog.

### Test Step Pre-condition:



### Test Step: