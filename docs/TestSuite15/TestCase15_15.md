## Test Case 15.15

> Editing a brand-new end user BCCP

Pre-condition: The brand-new BCCP is created by the end user and it is in the WIP state. The end user accesses these functionalities by opening the brand-new BCCP from the CC list page or after creating a brand-new BCCP.

### Test Assertion:

#### Test Assertion #1
The end user can change the properties of the BCCP and save the changes with the following business rules.

	1. The fields “Property Term”, “Nillable”, “Namespace”, “Value Constraint (Default or Fixed Value)”, “Definition”, “Definition Source” can be changed.
	2. The field “DEN” is automatically changed based on the changes of the “Property Term” field.
	3. A warning should be given when the Definition is empty.
	4. The fields “GUID” and “DEN”, and “Deprecated” cannot be changed.
	5. The fields of the BDT and its components cannot be changed.
	6. The fields “Default Value” and “Fixed Value” are mutually exclusive.
	7. The fields “Fixed Value” and “Nillable” are mutually exclusive.
	8. “Property Term”, “Nillable”, and “Namespace” are required. Only non-standard namespace shall be allowed.

#### Test Assertion #2
The end user can change the BDT to another one.

#### Test Assertion #3
When the BCCP DEN changes, all BCCs which uses the BCCP and whose revision numbers are 1 shall have their DEN update accordingly.

#### Test Assertion #4
Place holder for testing about history of BCCP when available.

#### Test Assertion #5
The end user can Exclude SCs or not from the Searching Field by checking or unchecking the “Exclude SCs” checkbox accordingly.

	1. If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
	2. If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field

### Test Step Pre-condition:



### Test Step: