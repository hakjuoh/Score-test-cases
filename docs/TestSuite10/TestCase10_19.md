## Test Case 10.19

> Editing a brand-new developer BCCP

Pre-condition: The brand-new BCCP is created by the developer and it is in the WIP state. The developer accesses these functionalities by opening the brand-new BCCP from the CC list page or after creating a brand-new BCCP according to Test Assertion #1 of the Test Case 10.18.



### Test Assertion:

1. The developer can change the properties of the BCCP and save the changes with the following business rules.
	1. The fields “GUID”, “DEN” and “Deprecated” cannot be changed.
	2. The fields “Property Term”, “Nillable”, “Value Constraint (Default or Fixed Value)”, “Namespace”, “Definition Source” and “Definition” can be changed. “Property Term”, “Nillable”, and “Namespace” are required.
	3. The field “DEN” is automatically changed based on the changes of the “Property Term” field.
	4. The fields “Default Value” and “Fixed Value” are mutually exclusive.
	5. The fields “Fixed Value” and “Nillable” are mutually exclusive.
	6. A warning should be given when the Definition is empty.
	7. The fields of the BDT and its components cannot be changed.
	8. Only standard namespace shall be allowed for the “Namespace”.
2. The developer can change the BDT to another one.
3. The developer can transfer ownership of the BCCP to another developer while in the WIP state but not end user.
4. When the BCCP DEN changes, all BCCs which uses the BCCP and whose revision numbers are 1 shall have their DEN updated accordingly.
5. The end user can Exclude SCs or not from the Searching Field by checking or unchecking the “Exclude SCs” checkbox accordingly.
	1. If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
	2. If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field

### Test Step Pre-condition:

1. There is a BCCP, say BCCP1, which is a brand new BCCP and it is in WIP state and owned by the developer conducting the test steps.

### Test Step:

1. An OAGi developer logs into the system.
2. The developer opens BCCP11019ow.
3. Verify that the GUID, DEN and Deprecated fields cannot be changed (they are disabled). (Assertion #1.1)
4. He changes all the fields expect “Nillable” checkbox (he leaves it unchecked). He also set Fixed value and updates the BCCP11019ow.
5. Verify that the BCCP11019ow been successfully updated. Also verify that the “DEN” field has updated based on new “Property Term”. (Assertion #1.2, 1.3)
6. He sets the Default value and updates the BCCP11019ow.
7. Verify that he cannot set the “Fixed value” (there is no such field if he selects the “Default value” field of the selector list) and that the BCCP11019ow has been successfully updated. (Assertion #1.4)
8. He checks the “Nillable” field.
9. Verify that he cannot select the “Fixed Value” field (he cannot click on that field of the selector list). (Assertion #1.5)
10. He leaves the “Definition” field blank.
11. Verify that a warning message is returned saying that the “Definition” field has been left blank. (Assertion #1.6)
12. Verify that he cannot change the fields of the BDT. (all of them are disabled) (Assertion #1.7)
13. He changes the BDT of the BCCP11019ow (e.g., he uses the BDT “Telephone Value. Type”)
14. Verify that the BDT has been changed (e.g., by checking that the “Number Format. Value” exists) (Assertion #2)
15. ..
16. The developer visits the CC list page and click on the Transfer ownership button of the BCCP11019ow.
17. Verify the in the dialog box there is no end user account displayed. (Assertion #4)
18. He chooses the developer devx to transfer the ownership of the BCCP11019ow.
19. Verify that the belongs to the developer devx (e.g., by checking the owner field in the CC list page). (Assertion #4)
20. …