## Test Case 10.5

> Creating a new revision of a developer ACC

Pre-condition: N/A



### Test Assertion:

1. On the CC Detail page of the working branch, the developer can create a new revision of an ACC that is in Published state regardless of the current owner. The result is that the working branch has that ACC and its associations with an incremental revision number that is in the WIP state.  Its detail attributes are initially the same as those of the previous revision.
2. A new revision CANNOT be made on an ACC in non-Published state.

### Test Step Pre-condition:

1. There is the ACC105a (e.g, OAGIS10 Nouns. Details) that is in Published Release state.

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the ACC105a and creates a new revision.
3. Verify that the fields are the same as those of the previous revision. (Assertion #1)
4. Verify that a new revision has been created. (e.g., by visiting the CC list page and verifying that the revision is greater than 1) (Assertion #1)