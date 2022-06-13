## Test Case 10.12

> Editing a brand-new developer ASCCP

Pre-condition: The brand-new ASCCP is created by the developer and it is in the WIP state. The developer accesses these functionalities by opening the brand-new ASCCP from the CC list page or after creating a brand-new ASCCP according to Test Assertion #1 in Test Case 10.9.

### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the ASCCP and save the changes with the following business rules.

	1. The fields “Property Term”, “Reusable”, “Nillable”, “Definition”, “Definition Source”, and “Namespace” can be changed.
	2. Deprecated field is locked at the value false.
	3. The field “DEN” is automatically changed based on the changes of the “Property Term” field.
	4. A warning should be given when the Definition is empty.
	5. The fields “GUID” and “DEN” cannot be changed.
	6. The fields of the Associated ACC and its children nodes cannot be changed.
	7. The following fields are required “Property Term”, “Reusable”, “Nillable”, and “Namespace”.
	8. The developer can choose a new ACC for the ASCCP. ASCCP DEN shall be automatically updated.
	9. Only standard namespace shall be allowed for the “Namespace”.

#### Test Assertion #2
The developer can transfer the ownership of an ASCCP, ONLY when it is in WIP states and owned by him, to another developer but not end user.

#### Test Assertion #3
If Object Class Term of the ACC used by the ASCCP changes, DEN of the ASCCP shall get updated. (This can occur only when both the ASCCP and ACC have revision #1.)

#### Test Assertion #4
When the ASCCP DEN changes, all ASCCs which uses the ASCCP and whose revision numbers are 1 shall have their DEN updated accordingly. (Note: I think updating ASCC DENs when opening the ACC owning them may not be a good option because the system has to make sure that ASSC DENs in any descendant ACC have to also be updated as the user keeps expanding the tree).

#### Test Assertion #5
The developer can change the underlying ACC to a new one. Only ACC whose component type is Semantics or Semantics Group can be selected. At least test that Extension ACC cannot be tested.

#### Test Assertion #6
The developer can Exclude SCs or not from the Searching Field by checking or unchecking the “Exclude SCs” checkbox accordingly.

	1. If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
	2. If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field

### Test Step Pre-condition:

1. There is the ASCCP11012ow that is in WIP state and owned by the developer of the test steps.
2. There is the ACC1012ow that is in WIP state, has revision number 1 and owned by the developer devx.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC list page and clicks on the ASCCP11012ow.
3. He changes the Property Term from ASCCP1012ow to ASCCP1012owchanged, he unchecks the Reusable field (makes it False), clicks on the Nillable field, sets a Definition to the Definition field and updates the ASCCP11012owchanged.
4. Verify that the ASCCP1012owchanged has been changed. (Assertion [#1](#test-assertion-1).1)
5. Verify that the Deprecated field is false. (Assertion [#1](#test-assertion-1).2)
6. He changes the Property Term back to ASCCP1012ow.
7. Verify that the DEN field has been changed accordingly. (Assertion [#1](#test-assertion-1).3)
8. The developer clears the Definition field and clicks update.
9. Verify that a warning message is returned. (Assertion [#1](#test-assertion-1).4)
10. He confirms its intension.
11. Verify that the Definition field is empty/blanck. (Assertion [#1](#test-assertion-1).4)
12. The developer enters a definition into the Definition field and updates the ASCCPow.
13. Verify that the ASCCP1012ow has been changed. (Assertion [#1](#test-assertion-1).4)
14. Verify that the GUID and DEN fields are disabled. (Assertion [#1](#test-assertion-1).5)
15. The developer expands the tree of the and clicks on its associated ACC
16. Verify that the details of the associated ACC and its child nodes are disabled. (Assertion [#1](#test-assertion-1).6)
17. The developer chooses a new ACC (e.g., the ACC1012ow) to associate it with the ASCCP1012ow.
18. Verify that the associated ACC has been changed. (Assertion [#1](#test-assertion-1).7)
19. Verify that the DEN field has been changed according to the Object Class Term of the new associated ACC. (Assertion [#1](#test-assertion-1).7)
20. The developer visits the CC list page.
21. He clicks on the menu used for transferring the ownership of the ASCCP1012ow.
22. Verify that no end user is displayed and so it cannot transfer the ownership of the to an end user. (Assertion [#2](#test-assertion-2))
23. He transfers the ownership to the developer devx.
24. The oagi developer logs out.
25. The developer devx logs into the score.
26. The visits the CC list page.
27. Verify that he owns the ASCCP1012ow. (Assertion [#2](#test-assertion-2))
28. He opens the ACC1012ow and changes its Object Class Term ACC1012ow from to ACC1012owchanged.
29. He visits the CC list page and clicks to view the ASCCP1012ow.
30. Verify that its DEN has been changed according to the ACC1012owchanged. (Assertion [#3](#test-assertion-3))
31. The developer creates the ACC21012ow and he appends the ASCCP11012ow
32. The developer opens the ACC11012owchanged and changes its object class term to ACC11012ow
33. The developer opens the ACC21012ow
34. Verify that the DEN field of its ASCC association has been changes accordingly. (Assertion [#4](#test-assertion-4))