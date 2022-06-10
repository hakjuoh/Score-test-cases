## Test Case 15.16

> Amend an end user BCCP

Pre-condition: N/A

Generally, only backwardly compatible changes can be made.

### Test Assertion:

1. On the CC Detail page of an end user BCCP in Production state, the end user even when he is not the owner can amend the BCCP. There should be a dialog asking the end user to confirm the intention to amend. [Note: In this case, the system simply advances the revision number, resets the revision tracking number to 1, and changes the state of the BCCP back to WIP.]  Its attributes are initially the same as before the amendment. [Note that I use the word ‘Amend’ as opposed to ‘Create a new Revision’ or ‘Revise’ as in the case of the developer CC, because in the case of the end user CC, the previous revision won’t be kept.]
2. The end user cannot amend a released developer BCCP.
3. The end user can change the details of the BCCP and save the changes with the following business rules.
	1. The fields “GUID”, “DEN”, “Namespace”, and “Property Term” cannot be changed.
	2. If a fixed value is already applied, it cannot be changed (hence neither default nor nillable can change).
	3. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the end user must be able to select a replacement BCCP that is not already deprecated from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	4. If nillable can change, it can only be changed from false to true.
	5. If the default value can change, it can change to any valid value w.r.t. the primitive.
	6. Definition and Definition Source can change.
	7. A warning should be given when the Definition is empty.
	8. The fields of the BDT and its supplementary components cannot be changed.
4. The end user cannot change the BDT to another one.
5. The end user can cancel the amendment, in which case, the system rollbacks all changes during the amendment. History changes are kept in the history record.
6. Place holder for testing about undoing changes to the BCCP or cancel the amendment in the future or about displaying history during the amendment.

### Test Step Pre-condition:



### Test Step: