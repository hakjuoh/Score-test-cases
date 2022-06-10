## Test Case 15.18

> Deleting an ender user BCCP

Pre-condition: N/A

Delete a CC means that it is marked as “Deleted” and it is still displayed in the CC list when the associated release branch is selected. If a CC is “Deleted” another end user can restore it. A confirmation dialog is needed for all deleting actions. “Do you really want to delete the core component?”

### Test Assertion:

1. If a BCCP revision number is 1, the end user who is the owner of the BCCP can delete it when it is in WIP state. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the CC list page.
2. Upon opening an ancestor ACC that has an ACC using a deleted BCCP, as the ancestor ACC is expanded down to the ACC that contains the deleted BCCP, the system shall be able to flag that the BCCP is in deleted state.
3. Upon opening an ACC that uses the BCCP, the BCC that uses that BCCP shall be highlighted or flagged somehow indicating that the BCC has a deleted BCCP. The system shall provide an option for the end user to choose another BCCP for the BCC. The system shall also allow the end user to open the deleted BCCP in another tab or dialog where he can restore it, even if the BCCP was is owned by another end user. Then, the system shall be able to clear the flag, e.g., when the end user refreshes the ACC.
4. BCCP whose revision number is more than 1 in any state cannot be deleted.

### Test Step Pre-condition:



### Test Step: