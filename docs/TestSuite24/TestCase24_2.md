## Test Case 24.2

> Create a Top-level BIE from a BIE node

Pre-condition: N/A
This functionality allows the user to create a top-level BIE from a descendant BIE node within a top-level BIE. The created top-level BIE may be reused within another top-level BIE afterward.


### Test Assertion:

#### Test Assertion #1
An end user opens a top-level BIE to view. The top-level BIE can be in any state and owned by anyone as long as it can be viewed by the end user. On any of the descendant ASBIE/ASBIEP/ABIE node that is not a reuse, the end user can invoke ‘Create top-level BIE’. Consequently:

	1. A top-level BIE is created based on the content of the selected ASBIEP. It shall be a copy of that ASBIEP.
	2. The newly created top-level BIE shall be in WIP state (after finish copying) and appear in the same release branch as the originating top-level BIE.
	3. The new top-level BIE is owned by the end user invoking the creation.

### Test Step Pre-condition:



### Test Step: