## Test Case 38.3

> Editing a brand-new developer DT

Pre-condition: The brand-new DT is created by the developer and is in the WIP state. The developer accesses these functionalities by opening the brand-new DT from the CC list page or after creating a brand-new DT according to the Test Case 38.2.

### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the DT and save changes with the following business rules.

	1. Namespace and Domain Value are required.  There should be a drop-down list for Namespace. A new value domain entry can be added, discarded, or Edited according to Test Case 38.8. Inherited domain value entry cannot be edited. Only Namespace that is a standard namespace shall be allowed.
	2. Qualifier can be updated such that it contains zero or more qualifiers in front of the qualifiers inherited from the based DT.
	3. Six digit identifier is optional.
	4. Content Component Definition, Definition and Definition Source are optional. However, A warning should be given when the Definition is empty.

#### Test Assertion #2
A new SC can be added to the DT and edited according to Test Case 38.4 and Test Case 38.5, respectively.

#### Test Assertion #3
. SC inherited from based DT can only be edited according to Test Case 38.7.

#### Test Assertion #4
Once the Update button is clicked, the changes, except Definition and Definition Source and Content Component Definition, must also be made to all DTs derived from this DT (test for at least 2 levels of derivations). Note that any restriction put upon this DT in the derived DT would be lost. There should be a confirmation dialog indicating this when the Update button was clicked – “Restrictions applied in all DT derived from this DT will be lost”. Definition, Definition Source, and Content Component Definition shall be propagated only if they were the same before the change. In other word, if these fields have been altered in the derived DTs before the change in this DT, leave the one altered alone. Note the loss is associated with only restrictions, i.e., new value domain added in the derived DT should not be loss/overwritten. Note that the Namespace should not be propagated to the derived DTs.

### Test Step Pre-condition:



### Test Step: