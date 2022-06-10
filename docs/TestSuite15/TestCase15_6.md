## Test Case 15.6

> Deleting an end user ACC

Pre-condition: N/A

Delete a CC means that it is marked as “Deleted” and it is still displayed in the CC list when the branch it belongs to is selected. If a CC is “Deleted” any other end user can restore it.

### Test Assertion:

1. If an ACC revision number is 1, the end user owner can delete it when it is in WIP state. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the CC list page.
2. Upon opening an ACC that has a descendant ACC that has a deleted ACC as a base, the system shall be able to flag that the descendant-based ACC is in deleted state. After the based ACC is replaced or resurrected, the end user should be able to see that reflected in the ACC tree (e.g., after clicking refresh).
3. Upon opening an ACC that uses a deleted ACC as a base, the system should flag that the based ACC is in deleted state. The system shall allow the end user to select a new ACC in the same release as a base or do away with the base. The system shall also allow the end user to open the deleted end user ACC to restore it. Then, the end user shall be able to see in the ACC detail page that the based ACC is no longer in the deleted state, e.g., after refreshing the ACC detail page.
4. Upon opening an ACC that has an association to an ASCCP that uses a deleted ACC, the system shall be able to flag that ACC as deleted. After the deleted ACC is resurrected or replaced, the end user shall be able to see that reflected in the ACC he has opened earlier, e.g., after refreshing the detail page.
5. Upon opening an ACC that has a descendant ACC that was deleted earlier used in in one or more associations, the system shall be able to flag the deleted ACC on those associations (for example in many BODs the same ACC such as customer party is used in both the header and the line components). After the deleted ACC is resurrected or replaced, the end user shall be able to see that reflected in the ACC he has opened earlier, e.g., after refreshing the ACC detail page.
6. Upon opening an ASCCP that uses the deleted ACC, the ASCCP shall be highlighted or flagged somehow indicating that the ASCCP is an invalid state. The system shall provide an option for the end user to choose another ACC, which can be an end user ACC or developer ACC. The system shall also allow the end user to open the deleted ACC in another tab where he can restore it. The end user may need to refresh the ASCCP detail page to clear the invalid flag.
7. ACC whose revision number is more than 1 and is in any state cannot be deleted.

### Test Step Pre-condition:



### Test Step: