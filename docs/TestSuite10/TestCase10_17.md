## Test Case 10.17

> Restoring a developer ASCCP

Pre-condition: The developer is on the CC View page with the working branch open. Some Deleted CCs are shown in the list may be with “Deleted” state is selected in the state filter box. The developer opens the ASCCP to see its detail.



### Test Assertion:

1. The developer user can restore a deleted ASCCP whose ACC is still alive.
2. The developer user can restore a deleted ASCCP whose ACC is deleted. The UI shall display a flag in the ASCCP detail page that the ASCCP is in an invalid state and that its ACC is in the deleted state.

### Test Step Pre-condition:

1. There is the ASCCP11017odel owned by the developer of the test steps and it is deleted.
2. There is the ASCCP21017devxdel owned by the developer devx and it is deleted.
3. There is the ACC31017odel owned by the developer of the test steps and it is deleted.
4. There is the ASCCP31017odel owned by the developer of the test steps, is in deleted state and uses the ACC11017odel which is deleted and owned by the same developer.

### Test Step:

1. The oagi developer logs into score.
2. He visits the CC list page, and filters CCs based on state “Deleted”.
3. He opens the ASCCP11017odel and restores it.
4. Verify that the has been active and that it is in WIP state. (Assertion #1)
5. The developer visits the CC list page and opens the ASCCP21017devxdel.
6. He tries to restore it.
7. Verify that there is no Restore button or it is disabled. (Assertion #1)
8. The developer visits the CC list page and opens the ASCCP31017odel.
9. He restores the ASCCP31017odel.
10. He expands the tree of the ASCCP31017odel.
11. Verify that there is a flag indicating that the ACC11017odel is deleted. (Assertion #2)