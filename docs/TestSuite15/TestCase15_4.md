## Test Case 15.4

> Amend an end user ACC

Pre-condition: The end user has selected a particular release branch.

Generally, only backwardly compatible changes can be made.

### Test Assertion:

1. On the CC Detail page of an end user ACC in Production state, the end user can amend the ACC. There should be a dialog asking the end user to confirm the intention to amend. [Note: In this case of amendment, the system simply advances the revision number, resets the revision tracking number to 1, and changes the state of the ACC back to WIP, i.e.,  detail of the previous revision of the ACC is not kept in the ACC table and it will not be possible to retrieve the whole structure of the previous revision of the ACC.]  Its attributes are initially the same as before the amendment.
2. The end user cannot amend a released developer ACC.
3. If ACC’s Component Type is User Extension Group, the end user cannot change/update any detail of the ACC.
4. If ACC’s Component Type is NOT User Extension Group, the end user can change the details of the ACC and save the changes with the following business rules.
	1. Component Type cannot be changed.
	2. Abstract can only be changed from True to False, except when the Component Type is base where it should be locked as True.
	3. “Namespace” and “Object Class Term” cannot be changed.
	4. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the end user must be able to select a replacement ACC in the same release that is not already deprecated from a drop-down list or search dialog in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	5. Definition and Definition Source can be changed. However, a warning should be given when the Definition is empty.
5. Place holder for testing about undoing changes to the ACC in the future or about displaying history during the amendment.

### Test Step Pre-condition:



### Test Step: