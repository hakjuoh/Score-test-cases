## Test Case 37.5

> End user Agency ID list state management

Pre-condition: The end user is on the Code List detail page, which he owns.
All these state changes need a confirmation dialog box “Do you want to change state of the Agency ID list to XYZ?”.


### Test Assertion:

#### Test Assertion #1
If there is no unsaved changes to the Agency ID list, the end user cannot change the state.

#### Test Assertion #2
Once changes to Agency ID list details or Agency ID list Value have been saved,

	1. The end user can change the Agency ID list state from WIP to QA.
	2. The end user can change the Agency ID list state from QA back to WIP.
	3. The end user can change the Agency ID list state from QA to Production.
	4. No state change can be in the Production state.
	5. The end user cannot change the Agency ID list state from WIP directly to Production.

### Test Step Pre-condition:



### Test Step: