## Test Case 10.3

> Editing a brand-new developer ACC

Pre-condition: The brand-new ACC is created by the developer and is in the WIP state. The developer accesses these functionalities by opening the brand-new ACC from the CC list page or after creating a brand-new ACC according to Test Assertion #1 of the Test Case 10.2.

### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the ACC and save changes with the following business rules.

	1. If the Component Type is base, Abstract shall be true and disabled.
	2. Abstract can only be true when the Component Type is base or Semantics.If it is Semantics Abstract should be enabled.
	3. Object Class Term, Component Type, Namespace, and Abstract are required.  There should be a drop-down list to select a namespace. Only Namespace that is a standard namespace shall be allowed. The following Component Type shall be disabled or hidden – Extension, User Extension Group, Embedded, OAGIS 10 Nouns, OAGIS 10 BODs.
	4. Deprecated must be false and locked b/c revision is 1.
	5. A warning should be given when the Definition is empty.
	6. If Object Class Term of the ACC change and there is one or more ASCCP depending on it, DEN of those ASCCP shall be updated accordingly, (Note: This should affect ASCCPs that are in revision 1 only.)
	7.  Only the following Component Type can be selected Base, Semantics, and Semantic_Group.

#### Test Assertion #2
When the Component_Type is Semantics, the developer can invoke a function/macro (maybe via a button next to the Component Type field) “Create Extension Component” to automatically create the extension component for the ACC. The application shall check whether there is already an association to an ASCCP whose property term is “Extension”. If so, notify the user “The ACC already has an extension component.”, and exit. If so, notify the user “The ACC already has an extension component.”, and exit. If not, create an association to the ASCCP as defined below and add, to the ACC, the association to the Extension ASCCP.

	1. The Extension ACC shall be created with the All Extension ACC as base. It shall have the Object Class Term = [Object Class Term of the current ACC] + “Extension”, the Component Type = Extension, and the namespace and owner is the same as that of the current ACC.
	2. The Extension ASCCP shall be created using the above Extension ACC. Its Property Term = “Extension”.
	3. The ASCC shall have zero to unbounded cardinality.
	4. The developer cannot create an OAGIS Extension if the ACC does not have a namespace (the ACC does not have namespace immediately after it is created).

#### Test Assertion #3
The developer can Exclude SCs or not from the Searching Field by checking or unchecking the “Exclude SCs” checkbox accordingly.

	1. If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
	2. If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field

### Test Step Pre-condition:

1. There is an ACC, say ACC103a, which is a brand new ACC and it is in WIP state
2. There is an ACC, say ASCCP103a, which is a brand new ASCCP, uses ACC103a and it is in WIP state
3. The working branch is selected

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the ACC103a.
3. He sets the Component Type to base.
4. Verify that the Abstract is True and checkbox is disabled. (Assertion [#1](#test-assertion-1).1)
5. He sets the Component Type to Semantics.
6. Verify that he can set Abstract (the checkbox is enabled). (Assertion [#1](#test-assertion-1).2)
7. He sets the Component Type to Extension.
8. Verify that he cannot set Abstract (the checkbox is disabled) and that the Abstract is False. (Assertion [#1](#test-assertion-1).2)
9. He sets the Component Type to Semantic Group.
10. Verify that he cannot set Abstract (the checkbox is disabled) and that the Abstract is False. (Assertion [#1](#test-assertion-1).2)
11. The developer sets the Namespace to a valid one (e.g., http://www.openapplications.org/oagis/10) and updates the ACC.
12. Verify that the ACC has been successfully updated. (Assertion [#1](#test-assertion-1).3)
13. The developer sets the Namespace to Null (e.g., “-“) and updates the ACC.
14. Verify that the Update button is disabled or that there is no null mat-select option. (Assertion [#1](#test-assertion-1).3)
15. The developer clicks on the Component Type selector.
16. Verify that the User Extension Group, Embedded, OAGIS 10 Nouns, OAGIS 10 BODs are disabled. (Assertion [#1](#test-assertion-1).3)
17. The developer tries to change Deprecated checkbox.
18. Verify that the Deprecated checkbox is disabled. (Assertion [#1](#test-assertion-1).4)
19. The developer leaves the Definition field empty and updates the ACC103a.
20. Verify that a warning message is returned. (Assertion [#1](#test-assertion-1).5)
21. The developer changes the Object Class Term of the ACC103a.
22. Verify that the DEN of the ASCCP103a has been changed accordingly. (Assertion [#1](#test-assertion-1).6)