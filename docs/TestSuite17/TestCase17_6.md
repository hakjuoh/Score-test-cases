## Test Case 17.6

> Deleting a Code List

Pre-condition: N/A
Delete a CL means that it is marked as “Deleted” and it is still displayed in the CC list when the release branch the code list belongs to is selected. If a CL is “Deleted” any other end user can restore it.


### Test Assertion:

#### Test Assertion #1
If an end user CL revision number is 1, the end user owner can delete it when it is in WIP state and is owned by him. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the View/Edit Code List page with the same release branch selected.

#### Test Assertion #2
Upon opening an end user BDT that uses a deleted CL, the system shall be able to flag that the CL is in deleted state. The system shall provide an option for the end user to choose another CL for the BDT. The system shall also allow the end user to open the deleted CL in another tab where he can restore it even if the end user is not the owner of that CL. Then, the system shall be able to clear the flag (e.g., when the developer refreshes the BDT). [This is not implementable until we have BDT Management Functionality.]

#### Test Assertion #3
End user CL whose revision number is more than 1 in any state cannot be deleted, check particularly the WIP state.

### Test Step Pre-condition:



### Test Step: