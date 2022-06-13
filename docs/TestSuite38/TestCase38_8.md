## Test Case 38.8

> Editing Value Domains

Pre-condition: The DT is in WIP state. This Test Case applies to value domain editing of both the DT content component and supplementary components, so each assertion needs to be tested for both the cases of content component and supplementary component.

### Test Assertion:

#### Test Assertion #1
The user can add a value domain that whose value domain type is a Code List or Agency ID List only if there is already a value domain whose type is Primitive and the CDT Primitive is Token.

	1. When a value domain is added and there is a DT that is based on this DT, the added value domain must be copied to derived DT.

#### Test Assertion #2
The user can discard a value domain, that is not inherited from based DT and that is currently not used as the default value domain.

	1. When the value domain is discarded, it has to also be discarded from all derived BDTs (test for when there is more than one derivation levels).

#### Test Assertion #3
The user cannot add a duplicate value domain.

#### Test Assertion #4
The user can change Default value domain. (Changing default value domain does effect derived BDTs).

### Test Step Pre-condition:



### Test Step: