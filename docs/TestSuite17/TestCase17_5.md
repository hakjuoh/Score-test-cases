## Test Case 17.5

> End user code list state management

Pre-condition: The end user is on the Code List detail page, which he owns.

All these state changes need a confirmation dialog box “Do you want to change state of the Code List to XYZ?”.

### Test Assertion:

1. If there is no unsaved changes to the CL, the end user cannot change the state.
2. Once changes to code list details or Code List Value have been saved,
	1. The end user can change the CL state from WIP to QA.
	2. The end user can change the CL state from QA back to WIP.
	3. The end user can change the CL state from QA to Production.
	4. No state change can be in the Production state.
	5. The end user cannot change the CL state from WIP directly to Production.

### Test Step Pre-condition:



### Test Step: