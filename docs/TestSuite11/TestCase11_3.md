## Test Case 11.3

> Editing a brand-new developer code list

Pre-condition: The brand-new CL is created by the developer and is in the WIP state. The developer accesses these functionalities by opening the brand-new CL from the CL View/Edit page or after creating a brand-new CL according to Test Assertion #1 of the Test Case 11.2.

### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the CL and save changes with the following business rules.

	1. The combination of List ID, Agency ID, and Version have to be unique in the working branch.
	2. Based Code List must be Null and locked.
	3. Name, List ID, Agency ID, Version, and Namespace are mandatory. Deprecated is also mandatory but must be false and locked.
	4. A warning should be given when the Definition is empty.
	5. Only standard namespace shall be allowed for the “Namespace”.
	6. The developer can add a Code List Value. The Code List Value can have the following field - Code, Short Name, Definition, Definition Source, and Deprecated. The Code field has to be unique within the CL. Deprecated field shall be false and locked.

#### Test Assertion #2
For Code List Value, only the Code and Short Name are required.

#### Test Assertion #3
A Code List Value can be removed.

#### Test Assertion #4
The developer can edit a Code List Value details except the Deprecated field with and without changing the Code field itself during the code list without base creation. Specifically verify that the deprecated flag is still locked when open a code value to edit.

#### Test Assertion #5
Code List Values shall be unique within the code list.

### Test Step Pre-condition:



### Test Step: