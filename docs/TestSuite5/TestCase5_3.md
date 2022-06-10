## Test Case 5.3

> OAGi developer's authorized management of business contexts

Pre-condition: N/A



### Test Assertion:

1. The OAGi developer can create a business context with only required information. See Create a Business Context in Score User Guide for Mandatory/Optional fields.
2. The developer can remove a context value during the business context creation.
3. The OAGi developer can create a business context with all information specified including those of the business context value table.
4. The OAGi developer cannot create a business context with missing required information.
5. The developer can see, in the business context list, all business context created by any user.
6. The OAGi developer can edit a business context created by any user.
7. The developer can update a business context with only required information.
8. The developer can update a business context with all information specified.
9. The developer cannot add a duplicate context value.
10. The developer cannot update a business context with missing required information.
11. The developer can discard a business context created by any user provided that there is no BIE referencing it.
12. The developer cannot discard a business context that a BIE is referencing it. The Discard button should be disable and there should be a tooltip on it providing the reason it cannot be deleted or what actions are needed to discard the BC.
13. The developer can update a business context created by any user, even when there is already a BIE referencing it. Verify that the business context name of the respective BIE has been updated accordingly.
14. The search feature is at least working including the exact match feature.
15. The developer can select a Business Context from the Business Context List page, navigate thought different paginator pages while the forenamed Business Context remains checked.
16. Verify that all the business context values (i.e., their Context Category, Context Scheme and Context Scheme Value) are listed in the Edit Business Context page.
17. In the dialog used for adding a business context value, verify that all the details of the Context Category, Context Scheme and Context Scheme Value are displayed.

### Test Step Pre-condition:

1. There are business contexts already created by various end users, say BCa and BCb, and also created by developers, namely BCx and BCy, with all fields populated. BCa and BCx are already used by a BIE. BCa has the name “Business Process Business Context”.

### Test Step:

1. An OAGi developer logs into the system.
2. The developer creates new business contexts, say BC0 and BC1, with the Name field specified. Also, he adds some business context values with all their fields specified to BC0 (but not to BC1). Moreover, he tries to add a new value which is the same as an existing one.
3. Verify that the BC0 and BC1 are successfully recorded by the application and that he couldn’t add a duplicate value. (Assertion #1, #9)
4. The developer creates a new business context, say BC2, with the Name field specified, while adding some business context values and removing some of them during the business’s context creation.
5. Verify that the business context is successfully recorded by the application (Assertion #2)
6. The developer creates a new business context, say BC3, with the Name field specified and adds some business context values, with all their fields specified.
7. Verify that the business context is successfully recorded by the application. (Assertion #3)
8. The developer tries to create a new business context leaving the Name field bank and without adding any business context values.
9. Verify that the Create button is disabled. (Assertion #4)
10. The developer tries to create a new business context, leaves the Name field blank and adds a business context value with all its fields specified.
11. Verify that the Create button is disabled. (Assertion #4)
12. The developer tries to create a new business context with the Name field specified and adds a business context value without any field specified.
13. Verify that the Add button is disabled. (Assertion #4)
14. The developer tries to create a new business context with the Name field specified and adds a value with all its fields specified except the context scheme value field.
15. Verify that the Add button is disabled. (Assertion #4)
16. The developer tries to create a new business context with the Name field specified and adds a value with only the context category field specified.
17. Verify that the Add button is disabled. (Assertion #4)
18. The developer visits the Business Context page.
19. Verify that he can see in the list BC0, BC1, BC2, BC3, BCa, BCb, BCx, and BCy. (Assertion #5)
20. The developer clicks to view BCa.
21. Verify that all fields are editable, and the Update button is present. (Assertion #6)
22. Go back to the Business Context page.
23. The developer clicks to view BC1.
24. Verify that fields are editable, and the Update button is present. (Assertion #6)
25. Go back to the Business Context page.
26. The developer clicks to view BC0.
27. Verify that fields are editable, and the Update button is present. (Assertion #6)
28. Go back to the Business Context page.
29. The developer clicks to view BCx.
30. Verify that fields are editable, and the Update button is present. (Assertion #6)
31. The developer changes the Name of the BC1 and clicks Update.
32. Verify that the BC1 has been successfully updated with the new content. (Assertion #7)
33. The developer clicks to view BCx.
34. The developer deletes all business context values so that only the mandatory Name field is present and clicks Update.
35. Verify that the BCx has been successfully updated with the new content. (Assertion #7)
36. The developer opens BC0.
37. He changes the content of the Name field, adds some business context values with all their fields specified and clicks Update.
38. Verify that BC0 is successfully updated with the new content. (Assertion #8)
39. The developer opens BC0.
40. He tries to add a duplicate value, namely a value that has the same Context Category, Context Scheme and Context Scheme value with an existing one.
41. Verify that the new value was not added. (Assertion #9)
42. The developer clicks to view BC0.
43. The developer removes the content of the Name field and tries to click update.
44. Verify that the Update button is disabled. (Assertion #10)
45. The developer undoes the changes of the previous step and tries to add a business context value without specifying its context.
46. Verify that the Add value button is disabled. (Assertion #10)
47. The developer undoes the changes of the previous step and tries to add a business context value without specifying its context scheme value.
48. Verify that the Add value button is disabled. (Assertion #10)
49. The developer undoes the changes of the previous step and tries to add a business context value with no field specified.
50. Verify that the Add value button is disabled. (Assertion #10)
51. The developer discards BC0.
52. Verify that BC0 is no longer on the Business Context page. (Assertion #11)
53. Go back to the Business Context page.
54. The developer clicks to view BCb.
55. The developer discards BCb.
56. Verify that BCb is no longer on the Business Context page. (Assertion #11)
57. Go back to the Business Context page.
58. The developer clicks to view BCa.
59. The developer tries to discard BCa.
60. Verify that the there is a tooltip providing the reason that the BCa cannot be discarded. (Assertion #12)
61. The developer clicks to view BCx.
62. The developer opens BCx, change the content of the Name field and clicks update.
63. Verify that BCx is successfully updated. Also, verify that the change is reflected to the BIE that uses the BCx (Assertion #13)
64. The developer visits the Business Context page.
65. He enters the keyword “userb” to the search drop-down box of the “Updater” search field.
66. Verify that the user “userb” appears only. Also verify that “oagi”, “devx” and “usera” users do not appear.
67. The developer clears everything, and he enters the search term “usiness” that is partially match some names of the business contexts.
68. Verify that at least BCa is returned. (Assertion #14)
69. The developer clears the search filters and he choose “oagis” as value of the Updater selector.
70. Verify that BCx is returned in the search result. (Assertion #14)
71. The developer clears the search filters and he choose today’s date as value of the Updated start date.
72. Verify that BCx is returned in the search result. (Assertion #14)
73. The developer clears all fields and enters the term “Process Business” to the Name field.
74. Verify that at least the BCa and the BCs are returned. (Assertion #14)
75. He clears the field and enters the term “”Process Business””.
76. Verify that the BCa is returned but not the BCs. (Assertion #14)
77. The developer visits the Business Context List page, he selects a Business Context (clicking the corresponding checkbox), goes to the next paginator pages and then returns back.
78. Verify that the checkbox of the selected Business Context is checked. (Assertion #15)