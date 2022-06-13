## Test Case 5.4

> Retired in 2.0-OAGi developer authorized access to code list management functions.

Pre-condition: N/A
There is an entire code list management test suite that replaces this test case.


### Test Assertion:

#### Test Assertion #1
The developer can create a code list without base with only required information. See Create a Brand New Code List in Score User Guide for Mandatory/Optional fields. In addition, Code list value cannot be duplicated.

#### Test Assertion #2
The developer can create a code list without base with all information specified and multiple code values.

#### Test Assertion #3
The developer can remove a code value during the code list without base creation.

#### Test Assertion #4
The developer cannot create a code list without base with missing required information including missing required information in the code value table.

#### Test Assertion #5
The developer cannot create a code list without base, when it does not meet a uniqueness constraint. See Create a Brand New Code List in Score User Guide for the uniqueness constraint.

#### Test Assertion #6
The developer can see, in the code list page, all code lists created by any user.

#### Test Assertion #7
The developer has access to edit an unpublished code list created by any user.

#### Test Assertion #8
The developer can view the detail of a published code list created by any user.

#### Test Assertion #9
The developer cannot update a published code list created by any user.

#### Test Assertion #10
The developer can update a code list without base, which has only required information including adding and removing code values.

#### Test Assertion #11
The developer can update a code list without base that has all information specified including adding and removing code values.

#### Test Assertion #12
The developer cannot update a code list without base that has missing required information including missing required information in the code value.

#### Test Assertion #13
The developer can publish a previously saved code list without base, which has only required information.

#### Test Assertion #14
The developer can publish a previously saved a code list without base with all information specified including those in code values.

#### Test Assertion #15
The developer cannot publish a previously saved code list without base that has missing required information including missing required information in the code value.

#### Test Assertion #16
Only published code lists without base can be used in BIE (and CC – we will not test for CC at this time as CC Editing function is not ready).

#### Test Assertion #17
The developer cannot discard a code list once it has been published.

#### Test Assertion #18
The developer can create a code list with base that has only required information. See Create a Brand New Code List in Score User Guide for Mandatory/Optional fields.

#### Test Assertion #19
The developer can create a code list with base with all information specified and with some code value restrictions and extensions added. The developer cannot change any field of the inherited code value.

#### Test Assertion #20
The developer can remove a code value during the code list with base creation.

#### Test Assertion #21
The developer cannot create a code list with base with missing required information including missing required information in the code value table.

#### Test Assertion #22
The developer cannot create a code list with base, when it does not meet a uniqueness constraint. See Create a Brand New Code List in Score User Guide for the uniqueness constraint.

#### Test Assertion #23
The developer can update a code list with base that has only required information including adding, removing and restricting, unrestricting code values. The developer cannot change any field of the inherited code value.

#### Test Assertion #24
The developer can update a code list with base that has all information specified including adding, removing, restricting, unrestricting code values. The developer cannot change any field of the inherited code value.

#### Test Assertion #25
The developer cannot update a code list with base that has missing required information including missing required information in the code value.

#### Test Assertion #26
The developer can publish a previously saved a code list with base.

#### Test Assertion #27
The developer cannot publish a previously saved code list with base that has missing required information including missing required information in the code value.

#### Test Assertion #28
Only published code lists with base can be used in BIE (and CC – we will not test for CC at this time as CC Editing function is not ready).

#### Test Assertion #29
Restricted code value in the base code list is displayed but cannot be enabled.

#### Test Assertion #30
The search feature is at least working.

#### Test Assertion #31
Only extensible code list can be a base code list.

#### Test Assertion #32
Unpublished code list cannot be used as a base.

#### Test Assertion #33
A confirmation message should be returned when creating a Code List with the same name as another Code List.

#### Test Assertion #34
A confirmation message should be returned when updating a Code List specifying a name which is the same with another Code List.

#### Test Assertion #35
The developer can select a Code List from the Code List page, navigate thought different paginator pages while the forenamed Code List remains checked.

#### Test Assertion #36
The developer can select a Code List Value from a Code List, navigate thought different paginator pages storing the code lists values while the forenamed Code List value remains checked.

### Test Step Pre-condition:

1. There are code lists already created by various end users, namely CLa and CLb, and also created by developers, namely CLx and CLy. CLa and CLx are in Editing state and they have all their fields specified including those of their code list values, whilst CLb and CLy are in Published state. CLx has the name “Code List Test Editing” and CLy has the name “Code List Testing”.
2. There is a code list that has all required information specified and the switch “Extensible” is not enabled so it cannot be extended. The name of the code list is “Non Extensible Code List” and it is in the Published state.
3. There is a BIE, namely BIEa, in Editing state and uses a node whose Primitive Type field can be set.

### Test Step:

1. An OAGi developer logs into the system.
2. The developer creates new code lists without base, say CL0 and CL1, with the Name, List ID, Agency ID, Version specified, while the Definition, Definition Source, Remark and the Extensible switch fields left blank. Moreover, he adds some code list values to CL0 (but not to CL1) with only their Code and Short Name fields specified. Also, he tries to add a new value with its properties same as an existing value.
3. Verify that both CL0 and CL1 are successfully recorded by the application and that he couldn’t add a duplicate value to CL0. (Assertion [#1](#test-assertion-1))
4. The developer creates a new code list without base, say CL2, with all data fields specified. Moreover, he adds multiple code list values with all their fields specified and he deletes some of these code list values during the creation of the code list.
5. Verify that the code list is successfully recorded by the application. (Assertion [#2](#test-assertion-2), [#3](#test-assertion-3))
6. The developer tries to create a code list without base with all fields specified except the Name field.
7. Verify that the “Create” button is disabled. (Assertion [#4](#test-assertion-4))
8. The developer tries to create a code list without base with all fields specified except the List ID field.
9. Verify that the “Create” button is disabled. (Assertion [#4](#test-assertion-4))
10. The developer tries to create a code list without base with all fields specified except the Agency ID field.
11. Verify that the “Create” button is disabled. (Assertion [#4](#test-assertion-4))
12. The developer tries to create a code list without base with all fields specified except the Version field.
13. Verify that the “Create” button is disabled. (Assertion [#4](#test-assertion-4))
14. The developer tries to create a code list without base with all fields specified, adds a new code list value with all its fields specified except the Code Field.
15. Verify that the “Add” button is disabled. (Assertion [#4](#test-assertion-4))
16. The developer tries to create a code list without base with all fields specified, adds a new code list value with all its fields specified except the Short Name Field.
17. Verify that the “Add” button is disabled. (Assertion [#4](#test-assertion-4))
18. The developer creates a code list without base, say CL3, with only the required field specified.
19. The developer creates a code list without base, say CL4 specifying only the required field but the List ID, Agency ID and Version fields are the same as those of the CL3.
20. Verify that the application indicates an error and that the new code list is not recorded By verifying that the CL4 is not displayed in the “Code Lists” page. (Assertion [#5](#test-assertion-5))
21. The developer visits the Code List page.
22. Verify that he can see in the list CL0, CL1, CL2, CLa, CLb, CLx, and CLy. (Assertion [#6](#test-assertion-6))
23. The developer clicks to view CLa.
24. Verify that all fields are editable, and the Update button is present. (Assertion [#7](#test-assertion-7))
25. The developer goes back to the Code List page.
26. Clicks to view CLx.
27. Verify that all fields are editable, and the Update button is present. (Assertion [#7](#test-assertion-7))
28. The developer goes back to the Code List page.
29. Clicks to view CLb.
30. Verify that no field is editable and that the Update, Discard and Publish buttons are not displayed. (Assertion [#8](#test-assertion-8), [#9](#test-assertion-9))
31. The developer goes back to the Code List page.
32. Clicks to view CLy.
33. Verify that no field is editable, and the Update, Discard and Publish buttons are displayed. (Assertion [#8](#test-assertion-8), [#9](#test-assertion-9))
34. Go back to the Code List page.
35. The developer clicks to view CL0.
36. The developer changes the content of the Name, List ID, Agency ID and Version fields, adds some code list values with only the Code and Short Name fields specified, removes some of these values and clicks Update. Also, he tries to add a new value with its properties same as an existing value.
37. Verify that CL0 is successfully updated with the new content and that he cannot add a duplicate value (Assertion [#7](#test-assertion-7), [#10](#test-assertion-10))
38. The developer clicks to view CL2.
39. The developer changes the content of all data fields including those of the Code List value table. Moreover, he adds and removes some code list values and clicks Update.
40. Verify that CL2 is successfully updated with the new content. (Assertion [#11](#test-assertion-11))
41. The developer clicks to view CLx.
42. The developer deletes the content of the Name field and clicks Update.
43. Verify that the “Update” button is disabled. (Assertion [#12](#test-assertion-12))
44. The developer undoes the changes of the previous step, deletes the content of the List ID field and tries to click Update.
45. Verify that the “Update” button is disabled. (Assertion [#12](#test-assertion-12))
46. The developer undoes the changes of the previous step, deletes the content of the Agency ID field and tries to click Update.
47. Verify that the “Update” button is disabled. (Assertion [#12](#test-assertion-12))
48. The developer undoes the changes of the previous step, deletes the content of the Version field and tries to click Update.
49. Verify that the “Update” button is disabled. (Assertion [#12](#test-assertion-12))
50. The developer undoes the changes of the previous step, deletes the content of the Code field of a Code List value and tries to click Edit.
51. Verify that the “Edit” button is disabled. (Assertion [#12](#test-assertion-12))
52. The developer undoes the changes of the previous step, deletes the content of the Short Name field of the Code List value and tries to click Edit.
53. Verify that the “Edit” button is disabled. (Assertion [#12](#test-assertion-12))
54. The developer goes back to the Code List page.
55. Clicks to view CL0.
56. The developer publishes the Code List.
57. Verify that the CL0 is in published state. (Assertion [#13](#test-assertion-13))
58. The developer clicks to view CLa.
59. The developer publishes the Code List.
60. Verify that the CLa is in published state. (Assertion [#14](#test-assertion-14))
61. The developer clicks to view CLx.
62. The developer deletes the content of the Name field and tries to publish it.
63. Verify that the “Publish” button is disabled. (Assertion [#15](#test-assertion-15))
64. The developer undoes the changes of the previous step, deletes the content of the List ID field and tries to publish it.
65. Verify that the “Publish” button is disabled. (Assertion [#15](#test-assertion-15))
66. The developer undoes the changes of the previous step, deletes the content of the Agency ID field and tries to publish it.
67. Verify that the “Publish” button is disabled. (Assertion [#15](#test-assertion-15))
68. The developer undoes the changes of the previous step, deletes the content of the Version field and tries to publish it.
69. Verify that the “Publish” button is disabled. (Assertion [#15](#test-assertion-15))
70. The developer undoes the changes of the previous step, deletes the content of the Code field of a Code List value and tries to click the “Edit” button.
71. Verify that the “Edit” button is disabled. (Assertion [#15](#test-assertion-15))
72. The developer undoes the changes of the previous step, deletes the content of the Short Name field of the Code List value and tries to click the “Edit” button.
73. Verify that the “Edit” button is disabled. (Assertion [#15](#test-assertion-15))
74. The developer goes to the List of BIEs page.
75. Clicks to view BIEa.
76. The developer expands the BIE tree, chooses a leaf node that has token as a default primitive, chooses Code as a Primitive type and tries to select “Code List Test Editing” as the content of the Code field.
77. Verify that the code List “Code List Test Editing” is not present in the list. (Assertion [#16](#test-assertion-16))
78. The developer goes to the Code List page.
79. Verify that the checkbox used to discard the CL0 is disabled. (Assertion [#17](#test-assertion-17))
80. Clicks to view CL0.
81. Verify that Discard button is absent. (Assertion [#17](#test-assertion-17))
82. The developer opens the CL1, turns on the Extensible switch, adds some code list values with only the Code and Short name fields specified and publishes the code list.
83. The developer goes to the Code List page.
84. Clicks to view CL1 and then he clicks the Derive Code List based on this button.
85. The developer clicks Save.
86. Verify that the code list, say CL1_e0, is successfully recorded by the application. (Assertion [#18](#test-assertion-18))
87. The developer goes back to the Code List page.
88. He opens and publishes the CL2.
89. He goes back to the Code List page.
90. Clicks to view CL2 and then clicks the Derive Code List based on this button.
91. Verify that the inherited code list values are not editable and so they cannot be changed (Assertion [#19](#test-assertion-19))
92. The developer restricts some code list values, adds some more, removes some of the added values, makes sure that all code list fields and code value fields are populated, and finally click Save to create a Code List, say CL2_e0. Also, he tries to add a new value with its properties same as an existing value.
93. Verify that the CL2_e0 is successfully recorded by the application and that he could not add a duplicate value. (Assertion [#19](#test-assertion-19), [#20](#test-assertion-20))
94. The developer access the code list with base creation by clicking “Code List” and “Create Code List from another” menu.
95. The developer search for CL2 and choose it as a base. (Assertion [#31](#test-assertion-31))
96. The developer specifies all fields except the Name field and tries to click the “Create” button.
97. Verify that the “Create” button is disabled. (Assertion [#21](#test-assertion-21))
98. The developer tries to create a code list with base (extending the CL2), with all fields specified except the List ID field.
99. Verify that the “Create” button is disabled. (Assertion [#21](#test-assertion-21))
100. The developer tries to create a code list with base (extending the CL2), with all fields specified except the Agency ID field.
101. Verify that the “Create” button is disabled. (Assertion [#21](#test-assertion-21))
102. The developer tries to create a code list with base (extending the CL2), with all fields specified except the Version field.
103. Verify that the “Create” button is disabled. (Assertion [#21](#test-assertion-21))
104. The developer tries to create a code list with base (extending the CL2), with all fields specified, adds a new code list value with all its fields specified except the Code Field.
105. Verify that the “Add” button is disabled. (Assertion [#21](#test-assertion-21))
106. The developer tries to create a code list with base (extending the CL2), with all fields specified, adds a new code list value with all its fields specified except the Short Name Field.
107. Verify that the “Add” button is disabled. (Assertion [#21](#test-assertion-21))
108. The developer tries to create a code list with base (extending the CL2), with all fields specified but the List ID, Agency ID and Version fields are the same as those of the CL3.
109. Verify that the application indicates an error and that the new code list is not recorded by verifying that it is not displayed in the “Code Lists” page. (Assertion [#22](#test-assertion-22))
110. The developer goes back to Code List page.
111. Clicks to view CL1_e0.
112. Verify that the code list values fields inherited from CL1 are not editable. (Assertion [#23](#test-assertion-23))
113. The developer changes the content of some fields, restricts some of the code list values, adds some more with all their fields specified, removes some of them and finally updates the code list.
114. Verify that the code list is successfully updated with the new content. (Assertion [#23](#test-assertion-23))
115. The developer goes back to Code List page.
116. Clicks to view CL2_e0.
117. Verify that the code list values fields inherited from CL2 are not editable. (Assertion [#24](#test-assertion-24))
118. The developer changes the content of some fields, restricts some of the code list values, adds some more with all their fields specified, removes some of them and finally updates the code list.
119. Verify that the code list is successfully updated with the new content. (Assertion [#24](#test-assertion-24))
120. The developer goes back to the Code List page.
121. Clicks to view CL1_e0.
122. The developer deletes the content of the Name field and tries to update the code list.
123. Verify that the “Update” button is disabled. (Assertion [#25](#test-assertion-25))
124. The developer undoes the changes of the previous step, deletes the content of the List ID field and tries to update the code list.
125. Verify that the “Update” button is disabled. (Assertion [#25](#test-assertion-25))
126. The developer undoes the changes of the previous step, deletes the content the Agency ID field and tries to update the code list.
127. Verify that “Update” button is disabled. (Assertion [#25](#test-assertion-25))
128. The developer undoes the changes of the previous step, deletes the content the Version field and tries to update the code list.
129. Verify that the “Update” button is disabled. (Assertion [#25](#test-assertion-25))
130. The developer undoes the changes of the previous step, adds a new code list value with all its fields specified except the Code field and tries to update the code list.
131. Verify that the “Add” button is disabled. (Assertion [#25](#test-assertion-25))
132. The developer undoes the changes of the previous step, adds a new code list value with all its fields specified except the Short Name field and tries to update the code list.
133. Verify that the “Add” button is disabled. (Assertion [#25](#test-assertion-25))
134. The developer goes back to Code List page.
135. Clicks to view CL1_e0.
136. The developer publishes the code list.
137. Verify that the code list is in Published state. (Assertion [#26](#test-assertion-26))
138. The developer goes back to the Code List page.
139. Clicks to view CL2_e0
140. The developer deletes the content of the Name field and tries to publish the code list.
141. Verify that the “Publish” button is disabled. (Assertion [#27](#test-assertion-27))
142. The developer undoes the change in the previous step and deletes the content of the List ID field and tries to publish the code list.
143. Verify that the “Publish” button is disabled. (Assertion [#27](#test-assertion-27))
144. The developer undoes the changes of the previous step, deletes the content the Agency ID field and tries to publish the code list.
145. Verify that the “Publish” button is disabled. (Assertion [#27](#test-assertion-27))
146. The developer undoes the changes of the previous step, deletes the content the Version field and tries to publish the code list.
147. Verify that the “Publish” button is disabled. (Assertion [#27](#test-assertion-27))
148. The developer undoes the changes of the previous step and tries to add a new code list value with all its fields specified except the Code field.
149. Verify that the “Add” button is disabled. (Assertion [#27](#test-assertion-27))
150. The developer undoes the changes of the previous step and tries to add a new code list value with all its fields specified except the Short Name field.
151. Verify that the “Add” button is disabled. (Assertion [#27](#test-assertion-27))
152. The developer goes to the List of BIEs page.
153. Clicks to view BIEa.
154. The developer expands the BIE tree, chooses a leaf node that has Primitive as Primitive Type and anything but token or string as Primitive (the reason to choose other primitive is for testing purpose only; this should work for any primitive), chooses Code as a Primitive Type and tries to select “Code List Test Editing” as the content of the Code field.
155. Verify that “Code List Test Editing” Code List is not present in the list and that the CL1_e0 is displayed. (Assertion [#28](#test-assertion-28))
156. The developer goes to the Code List page.
157. Clicks to view CL2_e0, he restricts some code values inherited from CL2 and he publishes the code list.
158. The developer creates a Code list based on CL2_e0, say CL2_e0e0.
159. Verify that the restricted code values of the CL2 are not displayed. (Assertion [#29](#test-assertion-29), [#21](#test-assertion-21))
160. The developer goes to the Code List page.
161. He enters the keyword “userb” to the search drop-down box of the “Updater” search field.
162. Verify that the user “userb” appears only. Also verify that “oagi”, “devx” and “usera” user does not appear.
163. He clears everything and he enters a search term “xtensibl” that partially matches some code list names.
164. Verify that at least the code list “Non Extensible Code List” is returned. (Assertion [#30](#test-assertion-30))
165. The developer selects “oagis” as Updater and clicks search button.
166. Verify that at least the code list “Non Extensible Code List” is returned. (Assertion [#30](#test-assertion-30))
167. The developer selects 1/1/2019 as Updated start date.
168. Verify that at least the code list “oacl_UnitCode” is returned. (Assertion [#30](#test-assertion-30))
169. He opens the code list CL2_e0e0 and he clicks on the Agency selector field.
170. He enters the keyword “FDA” to the search drop-down list input field.
171. Verify that the “US, FDA (Food and Drug Administration)” appears but not the “CCC (Customs Co-operation Council)”. (Assertion [#30](#test-assertion-30))
172. The developer clicks to view this code list.
173. Verify that the Create Code List based on this button is absent and so the code list cannot be extended. (Assertion [#31](#test-assertion-31))
174. Click on the menu Code List -> Create Code List based on Another. Enter in the search box “extensible”. (Assertion [#30](#test-assertion-30))
175. Verify that “Non Extensible Code List” does not show up for selection. (Assertion [#31](#test-assertion-31))
176. Ensure that CL2_e0e0 is extensible but unpublished.
177. The developer clicks to view CL2_e0e0.
178. Verify that the Create Code List based on this button is absent and so the code list cannot be extended. (Assertion [#32](#test-assertion-32))
179. Click on the menu Code List -> Create Code List based on Another. Use the Search box to find CL2_e0e0.
180. Verify that CL2_e1e1 does not show up for selection. (Assertion [#32](#test-assertion-32))
181. The developer creates a new code list, say CL5 without base specifying only the required fields and with the same name as the Code List CL2
182. Verify that a confirmation message is returned (Assertion [#33](#test-assertion-33)).
183. The developer confirms his intention.
184. Verify that the code list is recorded (Assertion [#33](#test-assertion-33))
185. The developer updates the new code list by changing the name to a new one which is the same as the code list “Non Extensible Code List”
186. Verify that a confirmation message is returned (Assertion [#34](#test-assertion-34))
187. The developer confirms his intention
188. Verify that the code list is updated (Assertion [#34](#test-assertion-34))
189. The developer creates a new code list, say CL2_e1 extending the CL2 Code List, specifying only the required fields and with the same name as the Code List CL2
190. Verify that a confirmation message is returned (Assertion [#33](#test-assertion-33)).
191. The developer confirms his intention.
192. Verify that the code list is recorded (Assertion [#33](#test-assertion-33))
193. The developer updates the code list CL2_e1 by changing the name to a new one which is the same as the code list “Non Extensible Code List”
194. Verify that a confirmation message is returned (Assertion [#34](#test-assertion-34)) where the developer confirms his intention
195. Verify that the code list is updated (Assertion [#34](#test-assertion-34))
196. The developer visits the Code List page, he selects a Code List (clicking the corresponding checkbox), goes to the next paginator pages and then returns back.
197. Verify that the checkbox of the selected Code List is checked. (Assertion [#35](#test-assertion-35))
198. The developer opens the Code List CL2_e0e0, he selects a Code List value (clicking the corresponding checkbox), goes to the next paginator pages and then returns back.
199. Verify that the checkbox of the selected Code List value is checked. (Assertion [#36](#test-assertion-36))