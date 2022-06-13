## Test Case 10.14

> Editing a revision of a developer ASCCP

Pre-condition: The ASCCP under test has revision number greater than 1 and is in WIP state.

### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the ASCCP and save the changes with the following business rules.

	1. The fields “GUID”, “Namespace”, and “Property Term” cannot be changed.
	2. “Definition” and “Definition Source” can be changed.
	3. If “Reusable” is false in the previous revision, it can be changed to true; otherwise, it cannot be changed.
	4. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement ASCCP that is not already deprecated from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	5. If “Nillable” is False, it can be changed to True but not vice versa.
	6. A warning should be given when the “Definition” is empty.
	7. The fields of the Associated ACC and its children nodes cannot be changed.

#### Test Assertion #2
The developer can change the ACC to another one.

#### Test Assertion #3
The developer can cancel the revision. In this case, the system rollbacks the ASCCP to the previous revision. There must be a confirmation dialog box. History of changes are in the history record.

### Test Step Pre-condition:

1. There are the following CCs:
2. ASCCP01014ow (e.g., Data Area. Sync RFQ Data Area) that is in WIP state and its revision number is 2. It is not Deprecated and its Nillable field is False.
3. ASCCP11014ow (e.g., Promotion Reference. Promotion Reference) that is in WIP state and its revision number is 2. It is not Deprecated and its Reusable and Nillable fields are True.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC List page and opens the ASCCP1014ow
3. Verify that the fields GUID and DEN are disabled. (Assertion [#1](#test-assertion-1).1)
4. Verify that the fields Namespace, Definition Source and Definition can be changed. (Assertion [#1](#test-assertion-1).2)
5. He changes the Namespace to “-“ as well as he makes some valid changes to the Definition Source and Definition fields. Finally, he updates the ASCCP1014ow.
6. Verify that the Namespace, Definition Source and Definition fields have been changed accordingly. (Assertion [#1](#test-assertion-1).2)
7. The developer opens the ASCCP1014ow.
8. Verify that the Reusable field is False and enabled. (Assertion [#1](#test-assertion-1).3)
9. He changes it to True and clicks the Update button.
10. Verify that the field has been changed. (Assertion [#1](#test-assertion-1).3)
11. The developer goes to CC list page and clicks to view ASCCP11014ow.
12. Verify that the Reusable field is True and disabled.
13. The developer goes back to CC list page and he opens the ASCCP11014ow.
14. …
15. Verify that the Nillable field can be changed. (Assertion [#1](#test-assertion-1).5)
16. He changes Nillable to True and clicks the Update button.
17. Verify that the ASCCP11014ow has been changed. (Assertion [#1](#test-assertion-1).5)
18. The developer visits the CC list page and opens to view ASCCP11014ow
19. Verify that the Nillable field is True and disabled. (Assertion [#1](#test-assertion-1).5)
20. The developer opens the ASCCP11014ow.
21. He clears the Definition field and clicks the Update button.
22. Verify that a warning message is returned asking him to confirm its intention. (Assertion [#1](#test-assertion-1).6)
23. He confirms its intension.
24. Verify that the Definition field is empty/blank. (Assertion [#1](#test-assertion-1).6)
25. The developer expands the ASCCP11014ow tree.
26. Verify that the details of its associated ACC cannot be changed. (Assertion [#1](#test-assertion-1).7)
27. Verify that the details of the nodes of its associated ACC cannot be changed. (Assertion [#1](#test-assertion-1).7)
28. The developer tries to change the associated ACC of the ASCCP11014ow.
29. Verify that there is no button used for changing the associated ACC. (Assertion [#2](#test-assertion-2))
30. …