## Test Case 34.4

> Editing a revision of a developer Agency ID List

Pre-condition: The Agency ID List under test has revision number greater than 1 and is in WIP state.

### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the Agency ID List and save changes with the following business rules.

	1. The Name, List ID, Agency ID and Namespace cannot be updated.
	2. Only Version, Definition and Definition Source can be updated.
	3. The combination of List ID, Agency ID and Version have to be unique in the working branch.

#### Test Assertion #2
Existing Agency ID List Values from the previous revisions cannot be discarded. Only their Meaning, Definition and Definition Source can be changed. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If Deprecated was false in the previous revision, the value can be deprecated. When the deprecated is changed from false to true, the developer can select one of Agency ID List Values as a replacement. When the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.

#### Test Assertion #3
A new unique Agency ID List Value can be added and all of its details can be edited, namely the Name and Definition fields. The deprecated field should be disabled because it is a new value.

#### Test Assertion #4
The system shall not allow a new Agency ID List Value that is a duplicate value within the Agency ID List; its name should be unique.

#### Test Assertion #5
A brand-new Agency ID List Value added in this revision can be discarded if it is not a replacement of a deprecated value. A dialog should tell the developer when the value cannot be removed because it is a replacement of a deprecated Agency ID List Value.

#### Test Assertion #6
The developer can cancel the revision. In this case, the system rollbacks the Agency ID List to the previous revision and its children Agency ID List Values back to the previous revision; The system also discard Agency ID List Values added in this revision. The changes made before cancellation are in the history record.

### Test Step Pre-condition:



### Test Step: