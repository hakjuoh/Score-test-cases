## Test Case 17.3

> Editing a brand-new end user code list

Pre-condition: The brand-new CL is created by the end user and is in the WIP state. The end user accesses these functionalities by opening the brand-new CL from the CL View/Edit page on a particular release branch or after creating a brand-new end user CL.

### Test Assertion:

#### Test Assertion #1
The end user can change the properties of the CL and save changes with the following business rules.

	1. The List ID, Agency ID, and Version have to be unique in the branch.
	2. Based Code List may be null or has a value but must be locked (because a based CL, if there is, would already be selected at this CL creation). Based code list is locked because code list is derived by copy. Changing this would mean recopying again, so it is better to deleted and create a new one.
	3. Name, List ID, Agency ID, Version, and Namespace. Deprecated is also mandatory but must be false (and locked). Namespace must be a non-standard namespace.
	4. A warning should be given when the Definition is empty.

#### Test Assertion #2
The end user can add a Code List Value. The Code List Value shall have the following field - Code, Short Name, Definition, Definition Source, and Deprecated. The Code field has to be unique within the CL and its based CL. Deprecated field shall be false and locked.

#### Test Assertion #3
For a CL with base, the end user can remove derived CL values and save.

#### Test Assertion #4
For a CL with base, the end user can change existing CL values and their details.

#### Test Assertion #5
For new Code List Value, only the Code and Short Name are required.

#### Test Assertion #6
An added Code List Value can be removed.

#### Test Assertion #7
The end user can edit a newly added Code List Value details except the Deprecated field with and without changing the Code field itself.

#### Test Assertion #8
The end user can select an end user Agency ID list in Production state under the Code List.

### Test Step Pre-condition:



### Test Step: