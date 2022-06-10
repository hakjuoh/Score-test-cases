## Test Case 11.7

> Deleting a Code List

Pre-condition: N/A

Delete a CL means that it is marked as “Deleted” and it is still displayed in the CC list when the working branch is selected. If a CL is “Deleted” any other developer can restore it. Generally, when the developer opens an entity containing a deleted entity at any level of the tree, the system shall flag the opened entity as in an invalid state and the deleted entity as in the deleted state.

### Test Assertion:

1. If a CL revision number is 1, the developer owner can delete it when it is in WIP state. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the View/Edit Code List page.
2. Upon opening a BDT that uses a deleted CL, the system shall be able to flag that the CL is in deleted state. The system shall provide an option for the developer to choose another CL for the BDT. The system shall also allow the developer to open the deleted CL in another tab where he can restore it. Then, the system shall be able to clear the flag (e.g., when the developer refreshes the BDT). [This is not implementable until we have BDT Management Functionality. Also note that on the CC side, by OAGIS import pattern code list can be used only thru a BDT. I.e., CL cannot be assigned directly to a BCCP.]
3. Upon opening an ACC (or ASCCP) which has a descendant (not direct child) ACC using a deleted CL, the ACC shall be flagged as in an invalid state. As the developer expands the tree down to the BCCP using the BDT that the deleted CL, the CL shall be flagged as deleted. The system shall also allow the developer to open the deleted CL in another tab where he can restore it. Then, the system shall be able to clear the flag (e.g., when the developer refreshes the BDT). [This is not implementable until we have BDT Management Functionality.]
4. CL whose revision number is more than 1 in any state cannot be deleted.

### Test Step Pre-condition:



### Test Step: