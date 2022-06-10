## Test Case 41.6

> Editing a brand-new SC

Pre-condition: A DT in WIP state is open and there exists a brand-new SC (locally/uninherited) added in the DT revision (first revision or a subsequent revision).



### Test Assertion:

1. The following fields can be edited with business rule checked either when field is updated or the Update button is clicked:
	1. Property Term: Property term shall be unique across all DT derived from this DT as well as within the DT itself. Required.
	2. Representation Term can be updated. Required. When the Representation Term is changed the Value Constraint should be reset.
	3. Cardinality = Optional or Required. Required.
	4. Value Constraint can be updated. Optional.
	5. Value Domain: Value Domain based on the selected Representation Term cannot be updated. New value domain can be added or discarded. Code List or Agency ID List value domain can be added only if there is a Token CDT Primitive in the value domains. A value domain with Token CDT Primitive cannot be discarded, if there a Code List or Agency ID List in the value domain – dialog shall indicate that this is the reason the value domain cannot be discarded. A value domain which is a default value domain cannot be discarded.
	6. Default value domain can be changed and must be chosen from an existing value domain. Default value domain is required.
	7. Definition and Definition Source can be updated and they are optional. Warning shall be given when Definition is empty.
2. Once the Update button is clicked, the changes, except Definition and Definition Source, must also be made to the corresponding SC in all DTs derived from this DT (test for at least 2 levels of derivations). Note that any restriction put upon this SC in the derived DT would be lost. There should be a confirmation dialog indicating this when the Update button was clicked – “Restrictions applied to this SC in all DT derived from this DT will be lost”. Definition and Definition Source shall be propagated only if they were the same before the change. In other word, if the Definition and Definition Source have been altered in the derived DTs before the change in this DT, leave the one altered alone. Note the loss is associated with only restrictions, i.e., new value domain added in the derived DT should not be loss/overwritten.

### Test Step Pre-condition:



### Test Step: