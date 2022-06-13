## Test Case 38.4

> Add a brand-new SC

Pre-condition: A DT in WIP state is open.

### Test Assertion:

#### Test Assertion #1
The developer can add an SC to the DT.

#### Test Assertion #2
Default values of the new SC shall be as follows.

	1. Object Class Term = [Data Type Term of the DT]. The field is not editable.
	2. Property Term = “Property Term” + [a number]. The number ensures the Property Term is unique. It shall be unique across all DT derived from this DT as well. This field is required.
	3. Representation Term = one of the values in the dropdown list. (The list contains Representation Terms from all CDTs). This field is required.
	4. Cardinality = Optional.  This field is required.
	5. Value Constraint = None.
	6. Value Domain is populated with entries based on the selected Representation Term. Since each Representation Term corresponds to a single CDT, value domains from the associated CDT are populated. These value domains are not editable.
	7. Default value domain is set to the one default one based on the Representation Term. This field is required.
	8. Definition and Definition Source = blank text. These two fields are optional but warning shall be given when the Definition is empty.

#### Test Assertion #3
The added SC is propagated to all DTs derived from the DT in which the SC is added.

### Test Step Pre-condition:



### Test Step: