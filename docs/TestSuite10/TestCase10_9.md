## Test Case 10.9

> Deleting developer ACC

Pre-condition: N/A
Delete a CC means that it is marked as “Deleted” and it is still displayed in the CC list when the working branch is selected. If a CC is “Deleted” any other developer can restore it. Delete also means the deleted information is kept in the ACC table. Generally, when an entity is opened that has a relationship (whether in association or in base relationship) to a deleted entity, the opened entity shall be flagged as in an invalid state. And once the user has expanded the tree down to the deleted entity, the deleted entity should be flagged as deleted. This is applied to all test cases related to deletions.


### Test Assertion:

#### Test Assertion #1
If an ACC revision number is 1, the developer owner can delete it when it is in WIP state. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the CC list page. The deleted ACC shall appear in the working branch CC list (even without the Deleted state filter).

#### Test Assertion #2
Upon opening an ACC that has a descendant ACC that has a deleted ACC as a base, the system shall be able to flag that the opening ACC is in an invalid state and flag that the descendant-based ACC is in the deleted state. After the based ACC is replaced or restored, the developer should be able to see that reflected in the ACC tree (e.g., after clicking refresh).

#### Test Assertion #3
Upon opening an ACC that uses a deleted ACC as a base, the system should flag that the opening ACC is in an invalid state and the based ACC is in the deleted state. The system shall allow the developer to select a new ACC as a base or do away with the base. The system shall also allow the developer to open the deleted ACC to restore it. The developer shall be able to see that the based ACC is no longer in the deleted state after the restoration.

#### Test Assertion #4
Upon opening an ACC that has an association to an ASCCP that uses a deleted ACC, the system shall be able to flag that the opening ACC is in an invalid state and the other ACC as in the deleted state. After the deleted ACC is restored or replaced, the developer shall be able to see that reflected in the ACC he has opened earlier (e.g., after refreshing the detail page).

#### Test Assertion #5
Upon opening an ACC that has a descendant ACC that was deleted earlier, the system shall be able to flag that the opening ACC is in an invalid state and the descendant ACC as in the deleted state. After the deleted ACC is resurrected or replaced, the developer shall be able to see that reflected in the ACC he has opened earlier (e.g., after refreshing the ACC detail page).

#### Test Assertion #6
Upon opening an ASCCP that uses the deleted ACC, the ASCCP shall be highlighted or flagged somehow indicating that the ASCCP is an invalid state and that the ACC is in the deleted state. The system shall provide an option for the developer to choose another ACC. The system shall also allow the developer to open the deleted ACC in another tab where he can restore it. The developer may need to refresh the ASCCP detail page to clear the invalid flag.

#### Test Assertion #7
ACC whose revision number is more than 1 and is in any state cannot be deleted.

### Test Step Pre-condition:

1. There is the ACC11019ow owned by the developer of the test steps and it is in WIP state.
2. There is the ACC11019od owned by the developer of the test steps and it is in Draft state.
3. There is the ACC11019oc owned by the developer of the test steps and it is in Candidate state.
4. There is the ACC11019orev2 owned by the developer of the test steps and it is in WIP state.
5. There is the ACC21019baseow owned by the developer of the test steps and it is deleted.
6. There is the ACC21019descow owned by the developer of the test steps, is in WIP state and uses the ACC21019baseow.
7. There is the ACC21019ow owned by the developer of the test steps, is in WIP state and uses the ACC21019descow.
8. There is the ACC21019newbaseow owned by the developer of the test steps and it is in WIP state.
9. There is the ACC31019ow owned by the developer of the test steps and it is in WIP state.
10. There is the ASCCP41019ow owned by the developer of the test steps and it is in WIP state. The has an association to the ACC40w that is deleted. The ASCCP41019ow is also used by the ACC41019ow.

### Test Step:

1. The oagi developer logs into score.
2. He visits the CC list page and opens the ACC11019ow.
3. He deletes the ACC11019ow.
4. Verify that that the CC list page is returned and that the is deleted. (Assertion [#1](#test-assertion-1))
5. He visits the CC list page, opens the ACC11019od and tries to delete it.
6. Verify that there is no Delete button or that it is disabled. (Assertion [#1](#test-assertion-1))
7. He visits the CC list page, opens the ACC11019oc and tries to delete it.
8. Verify that there is no Delete button or that it is disabled. (Assertion [#1](#test-assertion-1))
9. He visits the CC list page, opens the ACC11019orev2 and tries to delete it.
10. Verify that there is no Delete button or that it is disabled. (Assertion [#1](#test-assertion-1))
11. The developer visits the CC list page and opens the ACC21019ow.
12. He expands its tree. In particular, he expands the ACC21019descow.
13. Verify that there is a flag indicating that the ACC21019baseow is deleted. (Assertion [#2](#test-assertion-2))
14. The developer visits the CC list page, filters CC based on Deleted state, opens the ACC21019baseow and finally restores it.
15. The developer visits the CC list page and opens the ACC21019ow.
16. He expands its tree. In particular, he expands the ACC21019descow.
17. Verify that there is no a flag indicating that the ACC21019baseow is deleted. (Assertion [#2](#test-assertion-2))
18. The developer visits the CC list page and opens the ACC21019descow.
19. He changes its base from ACC21019baseow to ACC21019newbaseow.
20. The developer visits the CC list page and opens the ACC21019ow.
21. He expands its tree. In particular, he expands the ACC21019descow.
22. Verify that the ACC21019newbaseow is displayed. (Assertion [#2](#test-assertion-2))
23. The developer visits the CC list page and opens the ACC21019descow.
24. He deletes it.
25. He opens the ACC21019ow and expands its tree.
26. Verify that there is a flag indicating that the ACC21019descow is deleted. (Assertion [#3](#test-assertion-3))
27. The developer deletes the ACC21019descow from the ACC21019ow.
28. Verify that the ACC21019descow has been deleted and does not exist in the tree. (Assertion [#3](#test-assertion-3))
29. The developer chooses a new base ACC (e.g., Acknowledge Catalog Route. Details).
30. Verify that the new base ACC has been set. (Assertion [#3](#test-assertion-3))
31. The developer changes the base ACC again with the ACC31019ow.
32. He visits the CC list page and deletes the ACC31019ow.
33. He opens the ACC21019ow and he expands its tree.
34. Verify that there is a flag indicating that the ACC31019ow is deleted.
35. The developer visits the CC list page and opens the ACC31019ow.
36. He restores the ACC31019ow back.
37. Verify that the ACC31019ow is in WIP state.
38. The developer visits the CC list page and opens the ACC21019ow.
39. He expands its tree.
40. Verify that there is no flag indicating that the ACC31019ow is deleted. (Assertion [#3](#test-assertion-3))
41. The developer opens the ACC41019ow.
42. He expands its tree. In particular, he expands the ASCCP41019ow.
43. Verify that there is a flag indicating that the ACC410190w is deleted. (Assertion [#4](#test-assertion-4))
44. The developer visits the CC list page.
45. He opens the ACC41019ow and restores it.
46. The developer visits the CC list page and opens the ACC41019ow.
47. He expands its tree. In particular, he expands the ASCCP41019ow.
48. Verify that there is no flag indicating that the ACC41019ow is deleted. (Assertion [#4](#test-assertion-4))
49. The developer sets the ACC31019ow as the base of the ACC41019ow.
50. He visits the CC list page, opens the ACC31019ow and deletes it.
51. He then opens the ACC41019ow and expands its tree.
52. Verify that there is a flag indicating that the ACC31019ow is deleted. (Assertion [#5](#test-assertion-5))
53. The developer visits the CC list page, filters CCs based on the Deleted state and he opens the ACC31019ow.
54. He restores the ACC31019ow.
55. The developer visits the CC list page and opens the ACC41019ow.
56. Verify that there is no flag indicating that the ACC31019ow is deleted. (Assertion [#5](#test-assertion-5))
57. …
58. The developer opens an existing Published Release ACC (e.g., Acknowledge Employee Work Time. Details) and he creates a new revision.
59. He tries to delete it.
60. Verify that there is no Delete button or that it is disabled. (Assertion [#7](#test-assertion-7))
61. He moves the ACC to the draft state.
62. He tries to delete it.
63. Verify that there is no Delete button or that it is disabled. (Assertion [#7](#test-assertion-7))
64. He moves the ACC to the candidate state.
65. He tries to delete it.
66. Verify that there is no Delete button or that it is disabled. (Assertion [#7](#test-assertion-7))