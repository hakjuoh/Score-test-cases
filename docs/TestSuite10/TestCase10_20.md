## Test Case 10.20

> Creating a new revision of a developer BCCP

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
On the CC Detail page of a published BCCP in working branch, the developer can create a new revision of the BCCP. The result is that the Working branch has that BCCP with an incremental revision number that is in the WIP state.  Its attributes are initially the same as those of the previous revision.

### Test Step Pre-condition:

1. There is the BCCP2 that is in Published Release state.

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the BCCP2 and creates a new revision.
3. Verify that the fields are the same as those of the previous revision. (Assertion [#1](#test-assertion-1))
4. Verify that a new revision has been created. (e.g, by visiting the CC list page and verifying that the revision is greater than 1) (Assertion [#1](#test-assertion-1))