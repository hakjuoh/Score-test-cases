## Test Case 10.13

> Creating a new revision of a developer ASCCP

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
On the CC Detail page of a published working branch of an ASCCP (whose revision number is the same as that of the latest release), the developer can create a new revision of the ASCCP. The result is that the working branch has that ASCCP with an incremental revision number that is in the WIP state.  Its attributes are initially the same as those of the previous revision.

### Test Step Pre-condition:

1. There is the ASCCP11013 (e.g, OAGIS10 Nouns. OAGiS10 Nouns) that is in Published Release state.

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the ASCCP11013 and creates a new revision.
3. Verify that the fields are the same as those of the previous revision. (Assertion [#1](#test-assertion-1))
4. Verify that a new revision has been created (e.g., by visiting the CC list page and verifying that the revision is greater than 1) and that the ASCCP11013 is in WIP state. (Assertion [#1](#test-assertion-1))