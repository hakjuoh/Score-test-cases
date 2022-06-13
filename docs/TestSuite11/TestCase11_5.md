## Test Case 11.5

> Editing a revision of a developer code list

Pre-condition: The CL under test has revision number greater than 1 and is in WIP state.

### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the CL and save changes with the following business rules.

	1. There should not exist any Extensible checkbox.
	2. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be lock. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement CL that is not already deprecated from a drop-down list in the Replaced By field – but the field is optional. There can be only one replacement code list. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	3. The Based Code List, Name, List ID, Agency ID and Namespace cannot be updated.
	4. Only Version, Definition, and Definition Source can be updated.
	5. The combination of List ID, Agency ID, and Version have to be unique in the working branch.

#### Test Assertion #2
Existing Code List Value from the previous revisions cannot be removed. Only its Meaning, Definition, and Definition Source field can be changed. It can also be deprecated, if deprecated was false. If deprecated was true, the deprecated flag shall be locked. When the deprecated is changed from false to true, the developer can select one of its CL values as a replacement.

#### Test Assertion #3
A new unique Code List Value can be added and all of its details can be edited.

#### Test Assertion #4
The system shall not allow a new code value to be edited/updated such that it results in a duplicate value within the CL.

#### Test Assertion #5
A brand-new code list value added in this revision can be removed if it is not a replacement of a deprecated value. A dialog should tell the developer when the value cannot be removed because it is a replacement of a deprecated code list value.

#### Test Assertion #6
The developer can cancel the revision. In this case, the system rollbacks the CL to the previous revision and its children Code List Value back to the previous revision; The system also discard Code List Values added in this revision. The changes made before cancellation are also removed from the history record.

### Test Step Pre-condition:



### Test Step: