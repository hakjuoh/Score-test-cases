## Test Case 38.11

> Editing existing supplementary components of a revision of a developer DT

Pre-condition: The DT revision (> 1) is created by the developer and is in the WIP state. The developer accesses these functionalities by opening an DT revision (> 1) from the CC list page.

### Test Assertion:

#### Test Assertion #1
Property Term cannot be changed.

#### Test Assertion #2
Representation Term cannot be changed.

#### Test Assertion #3
Value domains inherited from the based SC cannot be changed.

#### Test Assertion #4
A new Code List or Agency ID List value domain can be added when there is a Token CDT Primitive in the existing value domain. And such locally-added value domain can be discarded.

#### Test Assertion #5
Default value domain can be changed.

#### Test Assertion #6
Cardinality can be only be changed only if the original value is optional. If the value was changed to required, it can be changed back to optional.

#### Test Assertion #7
Definition, and Definition Source can be edited.

#### Test Assertion #8
Once the Update button is clicked, the changes, except Definition and Definition Source, must also be made to the corresponding SC in all DTs derived from this DT (test for at least 2 levels of derivations). Note that any restriction put upon this SC in the derived DT would be lost. There should be a confirmation dialog indicating this when the Update button was clicked – “Extensions and restrictions applied to this SC in all DT derived from this DT will be lost”.  Definition and Definition Source shall be propagated only if they were the same before the change. In other word, if the Definition and Definition Source have been altered in the derived DTs before the change in this DT, leave the one altered alone. Note the loss is associated with only restrictions, i.e., new value domain added in the derived DT should not be loss/overwritten.

### Test Step Pre-condition:



### Test Step: