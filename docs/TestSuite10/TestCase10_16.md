## Test Case 10.16

> Deleting a developer ASCCP

Pre-condition: N/A

Delete a CC means that it is marked as “Deleted” and it is still displayed in the CC list when the working branch is selected. If a CC is “Deleted” any other developer can restore it.

### Test Assertion:

1. If an ASCCP revision number is 1, the developer owner can delete it when it is in WIP state. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the CC list page.
2. Upon opening an ancestor ACC that has an ACC using a deleted ASCCP, the ancestor ACC shall be flagged that it is in an invalid state. And as the ancestor ACC is expanded down to the ACC that contains the deleted ASCCP, the system shall be able to flag that the ASCCP has been deleted.
3. Upon opening an ACC that has an ASCC using a deleted ASCCP, the system shall be able to flag that the ACC is in an invalid state and that the ASCCP is in the deleted state. The system shall provide an option for the developer to choose another ASCCP for the ASCC. The system shall also allow the developer to open the deleted ASCCP in another tab where he can restore it. Then system shall be able to clear the flags afterward (e.g., when the developer refreshes the ACC).
4. ASCCP whose revision number is more than 1 and is in any state cannot be deleted.

### Test Step Pre-condition:

1. There is the ASCCP11016ow owned by the developer of the test steps that is in WIP state and its revision number is 1.
2. There is the ASCCP11016od owned by the developer of the test steps that is in Draft state and its revision number is 1.
3. There is the ASCCP11016oc owned by the developer of the test steps that is in Candidate state and its revision number is 1.
4. There is the ACC11016ow owned by the developer of the test steps that is in WIP state and uses the ASCCP11016ow.
5. There is the ASCCP2 (e.g., Acknowledge Credit Transfer. Acknowledge Credit Transfer) that is in WIP state and has a revision number 2.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC list page and he opens the ASCCP11016ow.
3. He clicks delete button.
4. Verify that a confirmation message is returned asking for his approval. (Assertion #1)
5. He verifies his intension.
6. Verify that the CC list page is returned and that the ASCCP11016ow is in Deleted state. (Assertion #1)
7. He opens the ASCCP11016od and tries to delete it.
8. Verify that there is no Delete button. (Assertion #1)
9. He opens the ASCCP11016oc and tries to delete it.
10. Verify that there is no Delete button. (Assertion #1)
11. The developer opens the ACC11016ow and expands its tree.
12. Verify that there is an indicator showing that the ASCCP11016ow is deleted. (Assertion #2)
13. The developer can change the ASCCP or the ASCC…..<- not yet implemented
14. …TA3??
15. The developer clicks on the flag which indicates that the ASCCP11016ow is deleted.
16. Verify that a new tab is created. (Assertion #3)
17. The developer restores the ASCCP11016ow.
18. He closes the new tab and goes to the first tab.
19. The developer refreshes the page (or he opens the ACC11016ow again)
20. Verify that there is no flag indicating that the is deleted. (Assertion #3)
21. The developer opens the ASCCP21016ow and tries to delete it.
22. Verify that there is no delete button. (Assertion #4)
23. The developer moves the ASCCP21016ow to the draft state and tries to delete it.
24. Verify that there is no delete button. (Assertion #4)
25. The developer moves the ASCCP21016ow to the candidate state and tries to delete it.
26. Verify that there is no delete button. (Assertion #4)