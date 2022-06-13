## Test Case 10.24

> Restoring developer BCCP

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
The developer user can restore a deleted BCCP whose BDT is still alive.

#### Test Assertion #2
The developer user can restore a deleted BCCP whose BDT is deleted. The UI display a flag in the BCCP detail page that its BDT is in deleted state.

### Test Step Pre-condition:

1. There is the BCCP11024odel owned by the developer of the test steps and it is deleted.
2. There is the BCCP21024devxdel owned by the developer devx and it is deleted.

### Test Step:

1. The oagi developer logs into score.
2. He visits the CC list page, and filters CCs based on state “Deleted”.
3. He opens the BCCP11024odel and restores it.
4. Verify that the has been active and that it is in WIP state. (Assertion [#1](#test-assertion-1))
5. The developer visits the CC list page and opens the BCCP21024devxdel.
6. He tries to restore it.
7. Verify that there is no Restore button or it is disabled. (Assertion [#1](#test-assertion-1))