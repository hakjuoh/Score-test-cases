## Test Case 10.10

> Restoring developer ACC

Pre-condition: The developer is on the CC View page with the Working branch open. Deleted CCs are shown in the list.

### Test Assertion:

#### Test Assertion #1
The developer user can open an ACC and restore it. All of its associations shall be restored as well. Revision number shall be the same as before restored. Note that the ASCCs and BCCs are restored not the corresponding ASCCPs and BCCPs.

### Test Step Pre-condition:

1. There is the ASCCP11010ow owned by the developer of the test steps and it is deleted.
2. There is the BCCP11010ow owned by the developer of the test steps and it is deleted.
3. There is the ACC11010ow owned by the developer of the test steps and it is deleted. The ACC11010ow uses the ASCCP11010ow and the BCCP11010ow.

### Test Step:

1. The oagi developer logs into score.
2. He visits the CC list page, and filters CCs based on state “Deleted”.
3. He opens the ACC1 and restores it.
4. Verify that the has been active and that it is in WIP state. (Assertion [#1](#test-assertion-1))
5. The developer expands the tree of the ACC11010ow.
6. Verify that the ASCCP11010ow and the BCCP1 1010ow are active and there is no flag indicating that are deleted. (Assertion [#1](#test-assertion-1))
7. The developer goes to CC list page.
8. He clicks to open the ASCCP11010ow.
9. Verify that is active and that is in WIP state. (Assertion [#1](#test-assertion-1))
10. The developer goes to CC list page.
11. He clicks to open the BCCP11010ow.
12. Verify that is active and that is in WIP state. (Assertion [#1](#test-assertion-1))