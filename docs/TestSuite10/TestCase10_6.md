## Test Case 10.6

> Editing a revision of a developer ACC

Pre-condition: The ACC under test has revision number greater than 1 and is in WIP state.

### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the ACC and save changes with the following business rules.

	1. Component Type cannot be changed.
	2. Abstract can only be changed from True to False, except when the Component Type is base where it should be locked as True.
	3. Object Class Term and Namespace cannot be changed.
	4. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement ACC that is not already deprecated in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI. When the Replaced By field has a value, it shall display the ACC’s Object Class Term and GUID.
	5. Definition and Definition Source can be changed. However, a warning should be given when the Definition is empty.

### Test Step Pre-condition:

1. There are the following CCs:
2. ACC106a (e.g., Collaboration Message. Details) that is in WIP state and its revision number is 1.
3. “Application Area Base. Details” with Component Type “Base (Abstract)” and Abstract False.
4. “Business Object Document. Details” with Component Type “Semantics” and Abstract False.
5. “Change Status Extension. Details” with Component Type “Extension” and Abstract False.
6. “Container Instance Identifiers Group. Details” with Component Type “Semantic Group” and Abstract False.
7. “Document Reference Base. Details” with Component Type “Base (Abstract)” and Abstract True.
8. “Currency Exchange ABIE. Details” with Component Type “Semantics and Abstract True.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC List page and opens the ACC106a
3. Verify that the Component Type is the same with the previous revision and that it cannot be changed. (Assertion [#1](#test-assertion-1).1)
4. He opens the “Application Area Base. Details” and creates a new revision.
5. Verify that the Component Type is “Base (Abstract)” and that the Abstract field is False and cannot be changed. (Assertion [#1](#test-assertion-1).2)
6. He opens the “Business Object Document. Details” and creates a new revision.
7. Verify that the Component Type is “Semantics” and that the Abstract field is False and cannot be changed. (Assertion [#1](#test-assertion-1).2)
8. He opens the “Change Status Extension. Details” and creates a new revision.
9. Verify that the Component Type is “Extension” and that the Abstract field is False and cannot be changed. (Assertion [#1](#test-assertion-1).2)
10. He opens the “Container Instance Identifiers Group. Details” and creates a new revision.
11. Verify that the Component Type is “Semantic Group” and that the Abstract field is False and cannot be changed. (Assertion [#1](#test-assertion-1).2)
12. He opens the “Document Reference Base. Details” and creates a new revision.
13. Verify that the Component Type is “Base (Abstract)” and that the Abstract field is True and cannot be changed. (Assertion [#1](#test-assertion-1).2)
14. He opens the “Currency Exchange ABIE. Details” and creates a new revision.
15. Verify that the Component Type is “Semantics” and that the Abstract field is True and it can be changed. (Assertion [#1](#test-assertion-1).2)
16. The developer changes Abstract to False and Updates the CC.
17. Verify that the CC has been successfully updated. (Assertion [#1](#test-assertion-1).2)
18. The developer opens the ACC106a.
19. Verify that the Object Class Term field is disabled. (Assertion [#1](#test-assertion-1).3)
20. Verify that the Deprecated field is enabled. (Assertion [#1](#test-assertion-1).4)
21. …..
22. The developer changes the Definition Source and the Definition field and Updates the ACC106a
23. Verify that the ACC106a has been updated. (Assertion [#1](#test-assertion-1).5)
24. The developer clears the Definition field and updates the ACC106a
25. Verify that a confirmation message saying that the definition is empty has been returned. (Assertion [#1](#test-assertion-1).5)
26. The developer confirms its intentions to leave the Definition field blank.
27. Verify that the ACC106a has been updated. (Assertion [#1](#test-assertion-1).5)