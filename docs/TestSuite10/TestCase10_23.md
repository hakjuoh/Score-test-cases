## Test Case 10.23

> Deleting developer BCCP

Pre-condition: N/A

Delete a CC means that it is marked as “Deleted” and it is still displayed in the CC list when the working branch is selected. Its detail can also be viewed. If a CC is “Deleted” any other developer can restore it as described in the following Test Case 10.24.

### Test Assertion:

1. If a BCCP revision number is 1, the developer owner can delete it when it is in WIP state. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the CC list page.
2. Upon opening an ancestor ACC that has an ACC using a deleted BCCP, the ACC should be flagged as it is in an invalid state and as the ancestor ACC is expanded down to the ACC that contains the deleted BCCP, the system shall be able to flag that the BCCP is in the deleted state. Test this for when there is a descendant ACC that is a group as well.
3. Upon opening an ACC that has a BCC using a deleted BCCP, the ACC shall be flagged as in an invalid state and the BCCP shall be flagged as in the deleted state. The system shall provide an option for the developer to choose another BCCP for the BCC. The system shall also allow the developer to open the deleted BCCP in another tab or dialog where he can restore it, even if the BCCP is owned by another developer. Then, the system shall be able to clear the flag, e.g., when the developer refreshes the ACC.
4. BCCP whose revision number is more than 1 in any state cannot be deleted.

### Test Step Pre-condition:

1. There is the BCCP11023ow owned by the developer of the test steps that is in WIP state and its revision number is 1.
2. There is the BCCP11023od owned by the developer of the test steps that is in Draft state and its revision number is 1.
3. There is the BCCP11023oc owned by the developer of the test steps that is in Candidate state and its revision number is 1.
4. There is the ACC11023ow owned by the developer of the test steps that is in WIP state and uses the BCCP11023ow.
5. There is the BCCP21023ow (e.g., Record Set Reference Id. Identifier) that is in WIP state and has a revision number 2.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC list page and he opens the BCCP11023ow.
3. He clicks delete button.
4. Verify that a confirmation message is returned asking for his approval. (Assertion #1)
5. He verifies his intension.
6. Verify that the CC list page is returned and that the BCCP11023ow is in Deleted state. (Assertion #1)
7. He opens the BCCP11023od and tries to delete it.
8. Verify that there is no Delete button. (Assertion #1)
9. He opens the BCCP11023oc and tries to delete it.
10. Verify that there is no Delete button. (Assertion #1)
11. The developer opens the ACC11023ow and expands its tree.
12. Verify that there is an indicator showing that the BCCP11023ow is deleted. (Assertion #2)
13. The developer clicks on the indicator.
14. Verify that a new tab is returned where the developer can view the BCCP11023ow.
15. He restores the BCCP11023ow and closes the new tab.
16. He refreshes the page where he viewed the ACC11023ow.
17. Verify that there is no indicator about that the BCCP11023ow is deleted. (Assertion #3)
18. The developer opens the BCCP21023ow and tries to delete it.
19. Verify that there is no delete button. (Assertion #4)
20. The developer moves the BCCP21023ow to the draft state and tries to delete it.
21. Verify that there is no delete button. (Assertion #4)
22. The developer moves the BCCP21023ow to the candidate state and tries to delete it.
23. Verify that there is no delete button. (Assertion #4)