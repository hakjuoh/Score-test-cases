## Test Case 37.3

> Editing a brand-new end user Agency ID list

Pre-condition: The brand-new Agency ID list is created by the end user and is in the WIP state. The end user accesses these functionalities by opening the brand-new Agency ID list from the Agency ID list View/Edit page on a particular release branch or after creating a brand-new end user Agency ID list.

### Test Assertion:

#### Test Assertion #1
The end user can change the properties of the Agency ID list and save changes with the following business rules.

	1. The List ID, Agency ID, and Version have to be unique in the branch.
	2. Based Agency ID list may be null or has a value but must be locked (because a based Agency ID list, if there is, would already be selected at this Agency ID list creation).
	3. Name, List ID, Agency ID, Version and Namespace are mandatory. Deprecated is also mandatory but must be false (and locked). Namespace must be a non-standard namespace.
	4. A warning should be given when the Definition is empty.

#### Test Assertion #2
The end user can add an Agency ID list Value. The Agency ID list Value shall have the following field - Value, Meaning, Definition, Definition Source and Deprecated. The Value field has to be unique within the Agency ID list and its based Agency ID list. Deprecated field shall be false and locked.

#### Test Assertion #3
For an Agency ID list with base, the end user can discard derived Agency ID list values and save.

#### Test Assertion #4
For an Agency ID list with base, the end user can change existing Agency ID list values and their details.

#### Test Assertion #5
For new Agency ID list Value, only the Value and Meaning are required.

#### Test Assertion #6
A newly added Agency ID list Value can be discarded. Application shall check for any references before discarding it, e.g., when it is being referenced as a replacement of a deprecated value, or when it is referenced in code list (this likely shouldn’t happen b/c code list agency ID field also has a logic to prevent this).

#### Test Assertion #7
The end user can edit a newly added Agency ID list Value details except the Deprecated field with and without changing the Value field itself.

#### Test Assertion #8
In the Agency ID field, the end user can select a value from the Agency IDs in the current list.

	1. When a new Agency ID is added to the list, the end user must be able to use that ID in the Agency ID field.
	2. When the end user tries to discard an Agency ID in the list and it is used in the Agency ID field, the application must prevent that from happening. I.e., show a dialog box indicating that the Agency ID is used in the Agency ID field and cannot be deleted.

### Test Step Pre-condition:



### Test Step: