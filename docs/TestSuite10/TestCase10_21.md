## Test Case 10.21

> Editing a revision of a developer BCCP

Pre-condition: The BCCP under test has revision number greater than 1 and is in WIP state.



### Test Assertion:

1. The developer can change the details of the BCCP and save the changes with the following business rules.
	1. The fields “GUID”, “DEN”, “Namespace”, and “Property Term” cannot be changed.
	2. If a fixed value is already applied, it cannot be changed (hence neither default nor nillable can change).
	3. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement BCCP that is not already deprecated from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	4. If nillable can change (no fixed value and nillable is false), it can only be changed from false to true.
	5. If the default value can change (no fixed value), it can change to any valid value w.r.t. the primitive.
	6. Definition and Definition Source can change.
	7. A warning should be given when the Definition is empty.
	8. The fields of the BDT and its supplementary components cannot be changed.
2. The associated BDT can be changed.
3. The developer can cancel the revision. In this case, the system rollbacks the BCCP changes during the revision. History of those changes are in the history record. There must be a confirmation dialog box.

### Test Step Pre-condition:

1. There is a BCCP (e.g., Effectivity Relation Code. Code), say BCCP31021ow, which is in WIP state and has a revision number greater than 1 and owned by the developer conducting the test steps.

### Test Step:

1. An OAGi developer logs into the system.
2. The developer opens BCCP31021ow and changes the Definition Field.
3. Verify that the GUID, DEN and Property Term fields cannot be changed (they are disabled) and that the Definition field has been updated. (Assertion #1.1 1.6)
4. He opens the BCCP “Ownership Type Code” that has Nillable=False, he creates a new revision of it and he sets it to True.
5. Verify that the change has been successfully recorded. (Assertion # 1.4)
6. He opens the BCCP “Adjusted Invoice Total Amount” that has Nillable=True and he creates a new revision of it.
7. Verify that he cannot change it to False. (Assertion # 1.4)
8. The developer opens BCCP31021ow, changes the Default Value and Definition Source field, leaves the Definition field empty and updates it.
9. Verify that a Warning message is returned. Also, verify that the BCCP3 has been changed successfully. (Assertion #1.6 1.7)
10. Verify that the BDT fields cannot be changed. (Assertion # 1.8)
11. He changes the BDT of the BCCP31021ow
12. Verify that the BDT has been changed (e.g., by checking that the “Number Format. Value” exists) (Assertion #2)
13. …