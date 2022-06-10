## Test Case 41.7

> Editing an inherited SC in a brand-new DT or revised DT

Pre-condition: A DT in WIP state is open and there exists some SCs inherited from its based DT.



### Test Assertion:

1. Property Term cannot be changed.
2. Representation Term cannot be changed.
3. Value domains inherited from the based SC cannot be changed.
4. A new Code List or Agency ID List value domain can be added when there is a Token CDT Primitive in the existing value domain. And such locally-added value domain can be discarded.
5. Default value domain can be changed.
6. Cardinality can be only be changed only if the inherited value is optional. If the value was changed to required, it can be changed back to optional.
7. Value Constraint, Definition, and Definition Source can be edited.
8. Once the Update button is clicked, the changes, except Definition and Definition Source, must also be made to the corresponding SC in all DTs derived from this DT (test for at least 2 levels of derivations). Note that any restriction put upon this SC in the derived DT would be lost. There should be a confirmation dialog indicating this when the Update button was clicked – “Extensions and restrictions applied to this SC in all DT derived from this DT will be lost”.  Definition and Definition Source shall be propagated only if they were the same before the change. In other word, if the Definition and Definition Source have been altered in the derived DTs before the change in this DT, leave the one altered alone. Note the loss is associated with only restrictions, i.e., new value domain added in the derived DT should not be loss/overwritten.

### Test Step Pre-condition:



### Test Step: