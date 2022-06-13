## Test Case 11.4

> Creating a new revision of a developer code list

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
On the CL Detail page of the working branch, the developer can create a new revision of a published CL regardless of the current owner. The result is that the working branch has that CL and its code list values with an incremental revision number that is in the WIP state.  Its detail attributes are initially the same as those of the previous revision except the Version field. The Version field shall be default to the previous value suffixed with “_New”. All the Code List Values from the previous revisions shall be present.

### Test Step Pre-condition:



### Test Step: