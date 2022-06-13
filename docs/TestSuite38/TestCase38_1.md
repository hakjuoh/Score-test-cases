## Test Case 38.1

> DT access

Pre-condition: A working branch is selected.

### Test Assertion:

#### Test Assertion #1
The developer can see in the CC list page all DTs owned by any developer in any state.

#### Test Assertion #2
The developer can view and edit the details of a DT that is in WIP state and owned by him.

#### Test Assertion #3
The developer CAN view but CANNOT edit the details of a DT that is in WIP state and owned by another developer. However, he can add comments.

#### Test Assertion #4
The developer can view the details of a DT that is in Draft, Candidate, or Release Draft state not owned by him but he cannot make any change except adding comments.

#### Test Assertion #5
The developer can view the details of a Published DT owned by any developer, but he cannot make any change except adding comments or make a new revision of the DT.

#### Test Assertion #6
There must not be any end user DT in the Working branch.

#### Test Assertion #7
The developer can view details of a deleted DT owned by another developer.

#### Test Assertion #8
The developer cannot edit details of a deleted DT owned by him. He can add comments.

#### Test Assertion #9
The developer cannot edit details of a deleted DT owned by another developer. He can add comments.

#### Test Assertion #10
The developer can restore a deleted DT owned by him.

#### Test Assertion #11
The developer can restore a deleted DT owned by another developer.

#### Test Assertion #12
The developer can move states of several DTs owned by him in one shot on the view/edit CC page. Test for:

	1. Changing state from WIP to Draft
	2. Changing state from Draft to WIP
	3. Changing state from Draft to Candidate
	4. Transfer the ownership
	5. Deleting.

#### Test Assertion #13
The developer cannot move states of several DTs in one shot if all selected DTs are not owned by him.

### Test Step Pre-condition:



### Test Step: