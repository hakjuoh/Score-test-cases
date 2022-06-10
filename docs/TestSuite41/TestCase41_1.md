## Test Case 41.1

> DT access

Pre-condition: A release branch is selected.



### Test Assertion:

1. The end user can see in the CC list page all DTs owned by any end user in any state.
2. The end user can view and edit the details of a DT that is in WIP state and owned by him.
3. The end user CAN view but CANNOT edit the details of a DT that is in WIP state and owned by another end user. However, he can add comments.
4. The end user can view the details of a DT that is in QA, or Production not owned by him but he cannot make any change except adding comments.
5. The end user can view the details of a Published DT owned by any developer, but he cannot make any change except adding comments or make a new revision of the DT.
6. There must not be any developer DT in the Release branch not in Published state.
7. The end user can view details of a deleted DT owned by another end user.
8. The end user cannot edit details of a deleted DT owned by him. He can add comments.
9. The end user cannot edit details of a deleted DT owned by another end user. He can add comments.
10. The end user can restore a deleted DT owned by him.
11. The end user can restore a deleted DT owned by another end user.
12. The end user can move states of several DTs owned by him in one shot on the view/edit CC page. Test for:
	1. Changing state from WIP to QA
	2. Changing state from QA to WIP
	3. Changing state from QA to Production
	4. Transfer the ownership
	5. Deleting.
13. The end user cannot move states of several DTs in one shot if all selected DTs are not owned by him.

### Test Step Pre-condition:



### Test Step: