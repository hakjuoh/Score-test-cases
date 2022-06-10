## Test Case 15.12

> Amend an end user ASCCP

Pre-condition: The end user has selected a particular release branch.

Generally, only backwardly compatible changes can be made.

### Test Assertion:

1. On the CC Detail page of an end user ASCCP in Production state, the end user can amend the ASCCP. There should be a dialog asking the end user to confirm the intention to amend. [Note: In this case, the system simply advances the revision number, resets the revision tracking number to 1, and changes the state of the ASCCP back to WIP, i.e., there is no snapshot of the previous version kept in the ASCCP table.] Its attributes are initially the same as before the amendment.
2. The end user cannot amend a released developer ASCCP.
3. The end user cannot amend or see a User Extension Group ASCCP.
4. If the ASCCP is not a User Extension Group ASCCP, the end user can change some details of the ASCCP and save changes compliant to the following business rules.
	1. The fields “Property Term” and “Namespace” cannot be changed.
	2. “Definition” and “Definition Source” can change.
	3. If “Reusable” is false in the previous revision, it can be changed to true; otherwise, it cannot be changed.
	4. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be lock. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement ASCCP that is not already deprecated from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	5. If “NIllable” was False, it can be changed to True but not vice versa.
	6. A warning should be given when the “Definition” is empty.
	7. The fields of the Associated ACC and its children nodes cannot be changed.
	8. “Property Term”, “Reusable”, “Namespace”, and “Nillable” are required.
5. The end user cannot change the ACC to another one.
6. The end user can cancel the amendment, in which case, the system rollbacks all changes during the amendment. History records throughout the course of the amendment are in the history record.

### Test Step Pre-condition:



### Test Step: