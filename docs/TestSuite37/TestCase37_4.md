## Test Case 37.4

> Amend an end user Agency ID list

Pre-condition: The end user has selected a particular release branch.



### Test Assertion:

1. On the Agency ID list Detail page of an end user Agency ID list in Production state, the end user can amend the Agency ID list regardless of the current owner. The result is that the release branch has that Agency ID list is in the WIP state and the revision number incremented by 1.  Its detail attributes are initially the same as those of the previous revision. All the Agency ID list Values from the previous revisions shall be present.
2. The end user cannot amend a developer Agency ID list in the release branch.
3. The end user can change the properties of the Agency ID list and save changes with the following business rules.
	1. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False before the amendment the checkbox shall be enabled. When Deprecated is changed to True, the end user must be able to select a replacement Agency ID list that is not already deprecated from a drop-down list in the Replaced By field – but the field is optional. There can be only one replacement Agency ID list. When the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	2. Based Agency ID list,  Namespace, Name, List ID, and Agency ID cannot be changed. The Version field is initially set to pre-amendment + “New” (same as developer code list), but the user can change to anything
	3. Version, Definition, Definition Source and Remark can be changed.
4. Existing Agency ID list Values from the previous revisions and that are not inherited from base cannot be removed and only their Meaning, and Definition field can be changed. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If Deprecated was false in the previous revision, the deprecated field can be changed from false to true. When it is changed to true, the end user can select ONE replacement Agency ID list value from the Agency ID list. When the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
5. Agency ID list Values from the previous revisions and that are inherited from base cannot be removed and only their Meaning, and Definition field can be changed. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If Deprecated was false in the previous revision, the deprecated field can be changed from false to true. When it is changed to true, the end user can select ONE replacement Agency ID list value from the Agency ID list. When the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
6. A new Agency ID list Value can be added and all of its details can be edited.
7. A brand-new Agency ID list value added in this revision can be discarded, if it is not a replacement of a deprecated Agency ID list value.
8. The end user can cancel the amendment. In this case, the system rollbacks the whole Agency ID list details and children Agency ID list Values to the previous revision.

### Test Step Pre-condition:



### Test Step: