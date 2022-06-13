## Test Case 38.10

> Editing a revision of a developer DT

Pre-condition: The DT under test has revision number greater than 1 and is in WIP state.

### Test Assertion:

#### Test Assertion #1
Only the following can change.

	1. Definition, Definition Source, and Content Component Definition can be changed. A warning should be given when the Definition is empty.
	2. A value domain can be added per Test Case 38.9. And such newly added value domain can be discarded.
	3. A new SC can be added per Test Case 38.4, discarded per Test Case 38.5, and edited per Test Case 38.6.
	4. Existing SC can be edited per Test Case 38.12. It cannot be discarded.

#### Test Assertion #2
Once the Update button is clicked, all changes, except Definition, Definition Source, and Content Component Definition, shall be propagated to DTs derived from this DT. There should be a confirmation dialog indicating – “Restrictions applied to this SC in all DT derived from this DT will be lost”. Note the loss is associated with only restrictions, i.e., new value domain and SC added in the derived DT shouldn’t be lost. Once the Update button is clicked, the changes, except Definition and Definition Source, must also be made to all DTs derived from this DT (test for at least 2 levels of derivations). Note that any restriction put upon this DT in the derived DT would be lost. There should be a confirmation dialog indicating this when the Update button was clicked – “Restrictions applied in all DT derived from this DT will be lost”. Definition and Definition Source shall be propagated only if they were the same before the change. In other word, if these fields have been altered in the derived DTs before the change in this DT, leave the one altered alone. Note the loss is associated with only restrictions, i.e., new value domain added in the derived DT should not be loss/overwritten.

### Test Step Pre-condition:



### Test Step: