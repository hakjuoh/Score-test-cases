## Test Case 15.3

> Editing a brand-new end user ACC

Pre-condition: The brand-new ACC is created by the end user and is in the WIP state. The end user accesses these functionalities by opening the brand-new ACC from the CC list page or after creating a brand-new ACC.



### Test Assertion:

1. Component Type can only be either Base, Semantics, or Semantic Group.
2. If ACC’s Component Type is User Extension Group, the end user cannot change/update any detail of the ACC.
3. If the ACC’s Component Type is NOT User Extension Group, the end user can change properties of the ACC and save changes with the following business rules.
	1. If the Component Type is base, Abstract shall be true.
	2. Abstract can only be true when the Component Type is base or Semantics.
	3. Object Class Term, Component Type, Namespace, and Abstract are required.  Namespace must be a non-standard namespace (there should be a drop-down list to select a namespace). The following Component Type shall be disabled or hidden – Extension, User Extension Group, Embedded, OAGIS 10 Nouns, OAGIS 10 BODs.
	4. Deprecated must be false and locked b/c revision is 1.
	5. A warning should be given when the Definition is empty.
	6. If Object Class Term of the ACC change and there is one or more ASCCP depending on it, DEN of those ASCCP shall be updated accordingly, (Note: This should affect ASCCPs that are in revision 1 only.)
4. The end user can Exclude SCs or not from the Searching Field by checking or unchecking the “Exclude SCs” checkbox accordingly.
	1. If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
	2. If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field

### Test Step Pre-condition:



### Test Step: