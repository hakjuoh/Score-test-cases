## Test Case 17.4

> Amend an end user code list

Pre-condition: The end user has selected a particular release branch.



### Test Assertion:

1. On the CL Detail page of an end user CL in Production state, the end user can amend the CL regardless of the current owner. The result is that the release branch has that CL and its code list values with an incremental revision number that is in the WIP state.  Its detail attributes are initially the same as those of the previous revision. All the Code List Values from the previous revisions shall be present.
2. The end user cannot amend a developer code list in the release branch.
3. The end user can change the properties of the CL and save changes with the following business rules.
	1. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False before the amendment the checkbox shall be enabled. When Deprecated is changed to True, the end user must be able to select a replacement CL that is not already deprecated from a drop-down list in the Replaced By field – but the field is optional. There can be only one replacement code list. When the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	2. Based Code List, Namespace, Name, List ID, and Agency ID cannot be changed. The Version field is initially set to pre-amendment + “New” (same as developer code list), but the user can change to anything
	3. Definition, Definition Source, and Remark can be changed.
4. Existing locally defined (i.e., not inherited) Code List Value from the previous revisions cannot be discarded. Only its Short Name, Definition, and Definition Source field can be changed. If the Deprecated field was true in the previous revision, the field along with the Replaced By field shall be locked. If it was false before the amendment, the checkbox shall be enabled. When it is changed to true, the end user can select ONE replacement CL value from the CL.
5. For the Code List Value inherited from the based Code List, the values cannot be removed since it is an amended code list (i.e., revision > #1). Only its Short Name, Definition, and Definition Source field can be changed. If the Deprecated field was true in the previous revision, the field along with the Replaced By field shall be locked. If it was false before the amendment, the checkbox shall be enabled. When it is changed to true, the end user can select ONE replacement CL value from the CL.
6. A new Code List Value can be added and all of its details can be edited.
7. A brand-new code list value added in this revision can be discarded, if it is not a replacement of a deprecated code list value.
8. The end user can cancel the amendment. In this case, the system rollbacks the whole CL details and children Code List Values to the previous revision.
9. Test expressing BIE that uses an amended end user code list and make sure that it is generated with the expected differences. Test with end user code list that is based on a developer code list and one that has no based.

### Test Step Pre-condition:



### Test Step: