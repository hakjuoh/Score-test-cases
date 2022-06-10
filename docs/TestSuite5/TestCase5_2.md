## Test Case 5.2

> OAGi developer's authorized management of context schemes

Pre-condition: N/A



### Test Assertion:

1. The developer can create a context scheme with only required information. See the Score User Guide for Mandatory/Optional fields.
2. The developer can create a context scheme with all information specified.
3. Adding and removing scheme values on the creation page works.
4. The developer cannot create a context scheme with missing required information including those of a context scheme value.
5. The developer cannot create a context scheme when the uniqueness requirement is not met. See the design document for the uniqueness requirement.
6. The application gives correct warning when the developer tries to create a context scheme with the Scheme ID and Agency ID that are the same as those off an existing context scheme but gives a different Name.
7. The developer can see, in the context scheme list, all context schemes created by any user.
8. The developer can edit a context scheme created by any user.
9. The developer can update a context scheme with only required information.
10. The developer can update a context scheme with all information specified.
11. The developer cannot update a context scheme with missing required information.
12. The developer can discard context schemes created by any user provided that there is no business context referencing it.
13. The developer cannot discard a context scheme that has a business context referencing it. The system shall indicate business contexts referencing the context category when the developer tries to delete the context scheme. Checkbox is disabled.
14. The developer can update a context scheme created by any user, even when there is already a business context referencing it. Also, verify that the respective business context is updated accordingly.
15. The developer cannot remove a Context Scheme value if it is used by a Business Context.
16. The developer cannot add a duplicate context scheme value.
17. The search feature is at least working.
18. The developer can add to a context scheme code list values from Published or Production Code Lists. (The code values are simply copied into the context scheme). The fields Scheme ID, Agency ID and Version can be still changed. The developer shall be notified that existing values will be removed. Test for: 
	1. Developer code list in the latest release
	2. Developer code list in an older release
	3. End user code list the latest release that is derived from a developer code list
	4. End user code list in an older release that is derived from another end user code list
19. The developer can add to a context scheme code list values from Production End User Code Lists. Test for a non-latest release and the latest release. The fields Scheme ID, Agency ID and Version can be still changed.
20. The developer can change the context scheme values added by a code list.
21. The developer can add a value to a context scheme after he has loaded values from a code list.
22. The developer can delete a value from a context scheme added by a selected code list.
23. The developer cannot use the “Load from code list” function, if a value of this Context Scheme is used by a Business Context.
24. The developer can select a Context Scheme from the Context Scheme List page, navigate thought different paginator pages while the forenamed Context Scheme remains checked.

### Test Step Pre-condition:

1. There are context schemes already created by various end users, say CSa and CSb, and also created by developers, namely CSx and CSy, with all fields populated. CSa and CSx are already used by a business context. CSb has the name “Business Process Context Schema”. CSa has a value named “csaValue” which is used by a Business Context, say BCa.

### Test Step:

1. An OAGi developer logs into the system.
2. The developer creates new context schemes, say CS0 and CS1, with the Context Category, Name, Scheme ID, Agency ID, and Version specified with some texts, while leaving the Description field blank. Ensure that both CS0 and CS1 use context categories created by different users. Add some scheme values to CS1 (but not CS0) without specifying the meaning.
3. Verify that both CS0 and CS1 are successfully recorded by the application by verifying that their values exists both in the “Context Schemes” page and “Context Scheme Detail” page. (Assertion #1)
4. The developer creates a new context scheme, say CS2, with all data fields specified. Use a context category created by the developer himself. Add some scheme values with the meaning specified. During the creation, also do some scheme value deletions. Moreover, he tries to add a value that already exists.
5. Verify that CS2 is successfully recorded by the application and that he could not add one value more than one times. (Assertion #2, #3, #16)
6. The developer tries to create a new context scheme with all fields specified except the Context Category field.
7. Verify that the “Create” button is disabled. (Assertion #4)
8. The developer tries to create a new context scheme with all fields specified except the Name field.
9. Verify that the “Create” button is disabled. (Assertion #4)
10. The developer tries to create a new context scheme with all fields specified except the Scheme ID field.
11. Verify that the “Create” button is disabled. (Assertion #4)
12. The developer tries to create a new context scheme with all fields specified except the Agency ID field.
13. Verify that the “Create” button is disabled. (Assertion #4)
14. The developer tries to create a new context scheme with all fields specified except the Version field.
15. Verify that the “Create” button is disabled. (Assertion #4)
16. The developer tries to create a new context scheme with all fields specified by trying to add a new context scheme value with all fields specified except the value field.
17. Verify that the “Add” button value is disabled. (Assertion #4)
18. The developer tries to create a new context scheme by giving the Scheme ID, Agency ID, and Version the same as those of CS0.
19. Verify that the application indicates an error message to the extent that the same context scheme version cannot be created. (Assertion #5)
20. The developer creates a new context scheme and gives the Name, Scheme ID, Agency ID the same as those of CS0, while keeping the Version different.
21. Verify that the application gives a warning message to the extent that the user is creating a context scheme with the same attributes while giving a different name and that he/she should confirm his/her intention. Also verify that the new context scheme is successfully created. (Assertion #5)
22. The developer creates a new context scheme and gives the Scheme ID and Agency ID the same as those of CS0, while keeping the Name and Version different.
23. Verify that the application gives a warning message to the extent that the user is creating a context scheme with the same Scheme ID and Agency ID while giving a different name and that he/she should confirm the intention. Also verify that the new context scheme is successfully created. (Assertion #6)
24. The developer visits the Context Scheme page.
25. Verify that he can see in the list CS0, CS1, CS2,CS3, CSa, CSb, CSx, and CSy. (Assertion #7)
26. The developer clicks to view CSa.
27. Verify that fields are editable including those of its values, and that the Update and Discard buttons are present. (Assertion #8)
28. Go back to the Context Scheme page.
29. The developer clicks to view CSy.
30. Verify that fields are editable including those of its values, and the Update and Discard buttons are present. (Assertion #8)
31. The developer deletes all scheme values and Description so that only mandatory field is present; and click Update.
32. Verify that the context scheme has been successfully updated with the new content. (Assertion #9)
33. The developer opens CS0.
34. The developer populates all the data fields, adds some context scheme values to CS0 and clicks Update. Moreover, he tries to add a value that already exists.
35. Verify that CS0 is successfully updated with the new content and that he could not add a value that already exists. (Assertion #10, #16)
36. The developer opens CS0.
37. Changes the content of some fields of some context scheme values and clicks Update.
38. Verify that CS0 is successfully updated with the new content. (Assertion #10)
39. The developer tries to update CS0 with all fields specified except the Name field.
40. Verify that the Update button is disabled. (Assertion #11)
41. The developer tries to update CS0 with all fields specified except the Scheme ID field.
42. Verify that the Update button is disabled. (Assertion #11)
43. The developer tries to update CS0 with all fields specified except the Agency ID field.
44. Verify that the Update button is disabled. (Assertion #11)
45. The developer tries to update CS0 with all fields specified except the Version field.
46. Verify that the Update button is disabled. (Assertion #11)
47. The developer tries to update CS0 with all fields specified except the Value field of a Context Scheme Value.
48. Verify that the Edit button of the value is disabled. (Assertion #11)
49. The developer discards CS0 (which should have no business context using it).
50. Verify that CS0 is no longer on the Context Scheme page. (Assertion #12)
51. The developer opens CSx.
52. The developer tries to discard CSx.
53. Verify that the application shows an error message and that CSx still exists on the Context Scheme page. (Assertion #13)
54. The developer opens CSa and makes some valid updates.
55. Verify that CSa is successfully updated. Also, verify that the corresponding value of the BCa has been updated (i.e., the content of the Context Scheme and Context Scheme values fields has been changed) (Assertion #14)
56. The developer opens CSa.
57. The developer tries to discard a context scheme value of the CSa which is used by a Business Context.
58. Verify that the application shows an error message and that this value still exists. (Assertion #15)
59. The developer goes to the Context Scheme page and enter the keyword “usera” to the search drop-down box of the “Updater” search field.
60. Verify that the user “usera” appears only. Also verify that “oagi”, “devx” and the “userb” users do not appear. (Assertion #17)
61. The developer clears the field and enters an all lowercase search term “process”.
62. Verify that CSb is returned in the search result. (Assertion #17)
63. The developer clears the search filters and he choose devx as value of the Updater selector.
64. Verify that CSx is returned in the search result. (Assertion #17)
65. The developer clears the search filters and he choose today's date as value of the Updated start date selector.
66. Verify that CSx is returned in the search result. (Assertion #17)
67. The developer clears Name field and enters the term “Process Context”.
68. Verify that at least the “CSBusiness Process Schema Context” and the “CSBusiness Process Context Schema” are returned.  (Assertion #17)
69. The developer clears Name field and enters the term ““Process Context””.
70. Verify that at least the “CSBusiness Process Context Schema” is returned but not the “CSBusiness Process Schema Context”.  (Assertion #17)
71. The developer opens the Context Scheme CSy and clicks on the “Code List” field to select a code list to import values from.
72. He enters the keyword “dateformat” into the search drop-down list field.
73. Verify that the clm6DateFormatCode1_DateFormatCode appears but not the clm6TimeFormatCode1_TimeFormatCode. (Assertion #17)
74. The developer creates a Code List, say CL1CodeList, and adds some values into it.
75. He creates a new context scheme, say cscl1, and he chooses the code list clm6ConditionTypeCode1_ConditionTypeCode to add values from.
76. Verify that he cannot choose the CL1CodeList as it is in Editing state. (Assertion #18)
77. Verify that he cannot change the fields “Scheme ID”, “Agency ID” and “Version” as he has selected a code list to import values from. (Assertion #19)
78. He creates the context scheme by clicking the “Create” button.
79. Verify that the cscl1 was successfully created and that it contains all the values of the code list clm6ConditionTypeCode1. Also verify that the Agency ID and the Version are automatically stored, and they are the same as the Code list clm6ConditionTypeCode1_ConditionTypeCode. (Assertion #18)
80. The developer opens the context scheme cscl1 and tries to edit a value.
81. Verify that he cannot click on a value and that the dialog box used for editing values is not displayed. (Assertion #19)
82. The developer tries to add a new value.
83. Verify that the Add button is disabled. (Assertion #20)
84. He tries to remove a value.
85. Verify that the checkbox used for deleting context scheme values is disabled. (Assertion #21)
86. The developer opens CSa.
87. Verify that both the checkbox “Import from Code List” and the field where you can select a code list are disabled. (Assertion #22)
88. The developer opens BCa and adds a new value from cscl1.
89. He opens cscl1 and tries to uncheck the checkbox “Import from Code List” so that he can add more values.
90. Verify that the checkbox “Import from Code List” is disabled. (Assertion #22)
91. The developer tries to select another code list to add values from.
92. Verify that he cannot select another code list by verifying that the mat-select button used to select a code list is disabled. (Assertion #22)
93. The developer opens BCa and removes all its values.
94. The developer opens cscl1and use the “Import from Code List” checkbox and adds values from a different code list.
95. Verify that the cscl1 updated with the new values. (Assertion #22)
96. The developer opens cscl1, unchecks the "Import from Code List” and adds some values manually.
97. Verify that the cscl1 updated with the new values. (Assertion #22)
98. The developer opens CSa and tries to add values from another Code List.
99. Verify that the “Import from Code List” checkbox is disabled. (Assertion #23)
100. The developer removes all values and then adds values from a Code List. Afterwards, he updates the CSa.
101. Verify that the CSa has been updated successfully. (Assertion #23)
102. The developer creates a new Business Context and uses a value of the Context Scheme CSa.
103. He opens the Context Scheme CSa and tries to import values by selecting a different Code list.
104. Verify that the selector field used for selecting the Code List to import values from is disabled. (Assertion #24)
105. The developer visits the Context Scheme List page, he selects a Context Scheme (clicking the corresponding checkbox), goes to the next paginator pages and then returns back.
106. Verify that the checkbox of the selected Context Scheme is checked. (Assertion #25)