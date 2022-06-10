## Test Case 5.5

> OAGi ­­­­developer authorized management of BIE

Pre-condition: N/A



### Test Assertion:

1. The developer can create a BIE without restricting it based on ASCCP1 in the non-latest published release branch resulting in BIE1.
2. The developer can create a BIE without restricting it based on ASCCP1 that has its ACC1 revised in the latest published release branch resulting in BIE1.1. Also verify that BIE1.1 is different from BIE1 as expected (e.g., has additional descendant BIE nodes). Test for the cases where ACC1 has been revised by:
	1. Changed based ACC.
	2. Has additional BCC and ASCC.
	3. One of its BCCPs was revised to be NOT nillable.
	4. One of its ASCCPs was revised to be NOT nillable.

	5. Has an addition ASCC to an ASCCP that is a group.
	6. Max cardinality of a BCC and an ASCC changed from unbounded to 1.
	7. One of its BCCPs has its BDT changed.
	8. One of its BCCPs has its BDT that tied to a code list changed to another BDT tied to another code list (verified that code lists available in the BIE changes).
	9. One of its ASCCPs is deprecated.
	10. A new ASCC is inserted in between previously existed associations.
	11. One of its BCCPs has its default value revised from no default value to a default value.
3. The developer cannot create a BIE based on a working branch ASCCP.
4. The developer can see, in the BIE list page, all BIEs owned by any user.
5. The developer can view the details of a BIE that is in WIP state and owned by him.
6. The developer cannot view the details of a BIE that is in WIP state and owned by another user.
7. The developer can view the details of a BIE that is in QA state and owned by any user but cannot make any change.
8. The developer can view the details of a production BIE owned by any user but cannot make any change.
9. The developer can change the state of his own BIE, after all changes have been saved, from WIP to QA.
10. The developer cannot change BIE’s state from WIP to QA if he has already made some changes. BIE has been updated successfully.
11. The developer can change the state of his own BIE from QA back to WIP.
12. The developer can move his own BIE which is in QA state to Production state.
13. The developer cannot make any change to his own production BIE.
14. The developer can update his own BIE that is in WIP state.
15. The developer cannot update his own BIE which is in QA or production state.
16. The developer cannot discard a BIE owned by another user.
17. The developer cannot discard a Production BIE he owns.
18. The developer can discard his own BIE that is in WIP.
19. The developer can update a BIE, which has different type of nodes enabled, with all their fields specified with valid data type. During the creation, he expands the BIE tree and he enables and disables nodes using both the pane depicting the tree structure and the Details pane.
	1. For root BIE node, the following fields should be editable; Version, Status, Business Term, Remark and Context Definition.
	2. For ASBIE node, the following fields should be editable; Used, Min, Max, Nillable, Business Term, Remark and Context Definition. However, Nillable must be editable only if ASCCP’s Nillable is True. The default value of the following fields; Association Definition, Component Definition and Type Definition, should be properly derived from the based CC.

	3. For BBIE and SC nodes, the following fields should be editable; Used, Min, Max, Nillable, Fixed Value, Business Term, Remark, Value Domain Restriction and Context Definition. However, Nillable must be editable only if BCCP’s Nillable is True. The default value of the following fields; Association and Component Definition, should be properly derived from the based CC.
20. The developer cannot update a BIE, which has different types of nodes enabled, by specifying Min and Max fields with invalid data types (String instead of Integer) including leaving them unspecified. The only string value that he can type is “unbounded” to the Cardinality Max field.
	1. When the original Min Cardinality is 0, the developer can specify 1.
	2. When the original Min Cardinality is 0 and Max Cardinality is unbounded, the developer can change the Min to any integer more than zero.
	3. When the original Min Cardinality is 0 and Max Cardinality is 1, the developer can change the Max to 0. And the application shall give warning if the Context Definition field is blank.
	4. When the original Min Cardinality is 1, the Min or the Max cannot be changed to zero.
	5. Min Cardinality cannot be changed to -1 or -5.
	6. When the original Min Cardinality is 0 and Max Cardinality is unbounded or -1, the developer can change Max to any number between (0, and INF).
	7. The developer can never change the Min to be more than the Max.
	8. The developer can set the Max cardinality to -1.
	9. The developer can set the Max cardinality to “unbounded”.
21. The developer cannot update a BIE, which has different types of nodes enabled,
	1. By specifying Value Domain Type field but not its corresponding field, namely Value Domain.
	2. Using an incompatible primitive with the based CC, when Value Domain is selected for Value Domain Type (i.e., only compatible value domains shall be offered in the dropdown list).
	3. Using an incompatible code list with the based CC, when Code is selected for Value Domain Type (i.e., only compatible code lists shall be offered in the dropdown list).
22. A code list which is an extension of a default code list (aka compatible code lists) used by a BBIE must show up for the code list selection, when the Value Domain Type is set to “Code”. Specifically:
	1. Only published, compatible code lists in the same release as the BIE shall be included, i.e., a code list exists only in a newer release shall not be included. The version of the code list should be also displayed.
23. The developer cannot update a BIE by changing the fields of a node that is not used.
24. The developer can hide and unhide unused nodes in the BIE tree.
25. The developer cannot copy a BIE created by another user and which is in the WIP state.
26. The developer can copy a BIE that he owns, and which is in WIP state.
27. The developer can copy a BIE which is in QA or Production state and owned by another user. In case that the BIE is owned by an end user, any descendant BIEs added by the end user to the Extension BIEs are ignored.
28. The developer can transfer ownership of a BIE only to another developer.
29. The developer can transfer ownership of the BIE he owns only when it is in WIP state, i.e., not when it is in QA or Production state.
30. The search feature in the Create BIE page is at least working
31. The search feature in the BIE List page is at least working.
32. The search feature in the Copy BIE page is at least working.
33. A node cannot be expanded automatically if a same-name node has been expanded (git issue #653).
34. The number of BIEs in Copy BIE page are the same with the number of the BIEs displayed on the right bottom index of the page.
35. The developer can assign multiple business contexts to a BIE during the BIE creation.
36. The developer can assign multiple business contexts to a BIE in the WIP state he owns via updating it (via View/Edit BIE page).
37. The developer cannot assign multiple business contexts to a BIE not the WIP state.
38. The developer cannot assign multiple business contexts to a BIE in not the WIP state and he does not own via updating it (via View/Edit BIE page).
39. The developer cannot assign the same business context more than one times in a BIE.
40. The developer can remove an assigned business context from a BIE in the WIP state he owns.
41. The developer cannot remove all business contexts from a BIE. There must be at least one business context assigned.
42. An example input text field should exist in BBIEPs and BBIE_SC where an example of data of node can be inserted.
43. The Fixed and Default values should be mutually exclusive.
44. If Cardinality Min is greater than zero in a BCC or an ASCC they must be enabled, and they cannot be disabled/unused. Their parent nodes can be unused though.
45. The developer can select a BIE from the BIE List page, navigate thought different paginator pages while the forenamed BIE remains checked.
46. The developer can neither create a local or global extension to the BIE.
47. The developer cannot create a BIE without a Business Context assigned.
48. The developer can set the Version metadata field and automatically the Fixed Value of the Version Identifier node is synchronized.
49. The developer can change the Fixed Value of the Version Identifier node even if it was previously synchronized.
50. The default value of the Primitive Date Time BCCPs should be date time.
51. Developer cannot create a new BIE from an ASCCP whose ACC has a group component type.
52. The developer can visit a BIE node and choose the option “Enable Children” in order to enable all Children nodes of this BIE node at once. The “Used” field of these nodes is checked.
53. The developer can visit a BIE node and choose the option “Set Max Cardinality 1” in order to set the Max Cardinality field of all the children nodes to 1.
54. The developer can click the Detail Reset button of a specific BIE node to reset the values back to initial the values of the BIE node. These values are based on the corresponding CC of the BIE node. A confirmation dialog should be also returned in order for the developer to confirm his intension of resetting the BIE node values
55. The developer can Exclude SCs or not from the Searching Field by checking or unchecking the “Exclude SCs” checkbox accordingly.
	1. If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
	2. If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field

### Test Step Pre-condition:

1. There are BIEs already created and owned by various end users, say BIEa, BIEb, BIEc, which are in editing, candidate and published state respectively.
2. There are BIEs already created and owned by a developer different than the one in the test steps below, say BIE0, BIE1 and BIE2, which are in editing state, candidate and published state respectively.
3. There is a BIE already created by the developer same as the one in the test step below, say BIE3, which is in candidate state and its Name is “Service Elements”.
4. There is an ASCCP with Property Term “Acknowledge Production Order”
5. There is the Module “Model\BODs\AcknowledgeProductionOrder”.
6. There is no extension to oacl_LanguageCode.

### Test Step:

1. An OAGi developer logs into the system.
2. The developer creates a BIE, say BIE4, with name “Cancel Require Product”, having chosen a Business Context and an ASCCP. Finally, he leaves the Edit BIE page having done no changes.
3. Verify that the BIE is successfully recorded by the application. (Assertion #1)
4. The developer visits the BIE List page.
5. Verify that he can see in the list BIE0, BIE1, BIE2, BIE3, BIE4, BIEa, BIEb and BIEc. (Assertion #2)
6. The developer clicks to view BIE4.
7. Verify that he can view the BIE4 and that he can expand the BIE tree so that the four different types of nodes are displayed (Assertion #3)
8. The developer goes back to the BIE List page.
9. He clicks to view BIEa.
10. Verify that he cannot view the BIEa by verifying that there is no link (<a>) to the BIEa and that he could not visit the Edit BIE page. (Assertion #4)
11. The developer clicks to view BIEb and tries to update it.
12. Verify that he can view the BIEb, but the fields of BIE’s nodes are not editable. (Assertion #5)
13. The developer clicks to view BIE1 and tries to update it.
14. Verify that he can view the BIE1, but the fields of BIE’s nodes are not editable. (Assertion #5)
15. The developer goes back to the BIE List page.
16. He clicks to view BIEc and tries to update it.
17. Verify that he can view the BIEc, but the fields of BIE’s nodes are not editable. (Assertion #6)
18. The developer goes back to the BIE List page.
19. He clicks to view BIE2 and tries to update it.
20. Verify that he can view the BIE2, but the fields of BIE’s nodes are not editable. (Assertion #6)
21. The developer goes back to the BIE List page.
22. The developer clicks to view BIE4, makes some changes, updates the BIE and then sets BIE’s state to Candidate.
23. Verify the BIE is successfully updated with the new content and that the BIE’s state is successfully recorded by the application. (Assertion #7)
24. The developer clicks to view BIE4, change it back to Editing state, reopen it and makes some changes.  (Assertion #9)
25. Verify that the Candidate button is present. (Assertion #8)
26. The developer clicks Update and then clicks Candidate.
27. He reopens BIE4 and he publishes it.
28. Verify that the BIE’s state is successfully recorded by the application. (Assertion #10)
29. He clicks to view BIE4.
30. Verify that the Back to Editing, Candidate and Publish buttons are not present and no field is editable. (Assertion #11)
31. The developer creates a new BIE, BIE5.
32. He clicks to view BIE5.
33. Verify that he can enable some nodes of the BIE and make some changes to them. Verify that the BIE has been stored successfully. (Assertion #12)
34. He sets the BIE’s state to candidate.
35. Verify that the fields of the BIE’s nodes are not editable. (Assertion #13)
36. He publishes the BIE5.
37. Verify that the fields of the BIE’s nodes are not editable. (Assertion #13)
38. The developer goes back to the BIE List page.
39. Verify that the Discard button is not enabled for BIEa, BIEb, BIEc, BIE0, BIE1, BIE2, BIE4 and BIE5. (Assertion #14, #15)
40. The developer creates BIE6.
41. The developer discards BIE6 by clicking the Discard button and accepting the warning message.
42. Verify that the BIE6 has  successfully been discarded by verifying it is not displayed in the BIE List page. (Assertion #16)
43. The developer discards BIE3 by clicking the Discard button and accepting the warning message.
44. Verify that the BIE3 has successfully been discarded by verifying it is not displayed in the BIE List page neither it is returned using the Property Term search field and searching for it. (Assertion #16)
45. The developer creates a BIE, say BIE7. Afterwards, he expands the BIE tree so that all different types of nodes are displayed and enables an ASBIE and a BBIE node by clicking its corresponding box existing in tree structure and an SC node using the Used checkbox. Finally, he updates the BIE.
46. Verify that the Version, Status, Business Term, Remark and Context Definition fields of the root BIE node are editable. (Assertion #17.1)
47. Verify that the Min, Max, Nillable, Business Term, Remark and Context Definition fields of the ASBIE node are editable and that the Association Definition, Component Definition and Type Definition fields are not. (Assertion #17.2)
48. Verify that the Min, Max, Nillable, Fixed Value, Business Term, Remark, Primitive Restriction and Context Definition fields of the BBIE node are editable and that the Association and Component Definition fields are not. (Assertion #17.3)
49. Verify that the Min, Max, Nillable, Fixed Value, Business Term, Remark, Primitive Restriction and Context Definition fields of the SC node are editable, and the Association and Component Definition fields are not. (Assertion #17.3)
50. The developer clicks Update, go to the BIE List page, and reopen BIE7.
51. Verify that the BIE7 is successfully updated with the new content specified in step 45. (Assertion #17)
52. The developer clicks to view BIE7 and enables different descendant nodes.
53. He tries to fill out the Min and Max fields with some string value.
54. Verify that a message is returned that the string value is not accepted and that the Update button is disabled. (Assertion #18)
55. He fills out the Max field with the value “unbounded”.
56. Verify that the field is successfully updated. (Assertion #18)
57. He deletes the content of Min and Max fields.
58. Verify that the application indicated an error and that the Update button is disabled. (Assertion #18)
59. The developer enables a node (e.g. Version Identifier) which has Min Cardinality 0 and changes its Min cardinality from 0 to 7 and clicks Update.
60. Verify that an error is returned and that the Update button is disabled (Assertion #18.1)
61. He enables some nodes with original Min Cardinality 0, he changes it to 1 and Updates the BIE.
62. Verify that the BIE is successfully updated with the new content. (Assertion #18.1 #18.2)
63. The developer enables a node (e.g. Intermediary) whose Min cardinality is 0 and Max is unbounded, sets its Min Cardinality to 10 and updates the BIE.
64. Verify that the BIE is successfully updated with the new content. (Assertion #18.2)
65. He sets the above Min Cardinality to -1.
66. Verify that the application indicates an error and that the Update button is disabled. (Assertion #18.2)
67. The developer enables a node (e.g. System Environment Code) whose Min Cardinality is 0, Max is 1 and the Context definition field is blank, set the Max Cardinality to 0 and updates the BIE.
68. Verify that the application gives a warning message that the Context Definition field is blank. (Assertion #18.3)
69. The developer enables a node (e.g. Release Identifier) whose Min and Max Cardinality are 1, sets the Min to 0 and updates the BIE.
70. Verify that the application indicates an error and that the Update button is disabled (Assertion #18.4)
71. Then he sets the Max Cardinality to 0.
72. Verify that the application indicates an error and that the Update button is disabled. (Assertion #18.4)
73. Then he sets Min Cardinality to -1.
74. Verify that the application indicates an error and that the Update button is disabled. (Assertion #18.5)
75. Then He sets Min Cardinality to -5.
76. Verify that the application indicates an error and that the Update button is disabled. (Assertion #18.5)
77. The developer enables a node (e.g. Intermediary) whose Min cardinality is 0 and Max is unbounded, sets Max Cardinality to 10 and updates the BIE.
78. Verify that the BIE is successfully updated with the new content. (Assertion #18.6)
79. He sets the Min Cardinality of a node (e.g. Release Identifier) to a higher value than the value of Max Cardinality.
80. Verify that the application indicates an error and that the Update button is disabled. (Assertion #18.7)
81. He sets the Max Cardinality of different nodes to -1.
82. Verify that the BIE is updated with the new content and that Max Cardinality field is set to “unbounded”. (Assertion #18.8)
83. He restores the previous values of the elements and he sets their Max Cardinality to “unbounded”.
84. Verify that the BIE is updated with the new content and that Max Cardinality field is set to “unbounded”. (Assertion #18.9)
85. The developer enables Creation Date Time node.
86. Set its Primitive Type to “Code” (without specifying a code).
87. He enables another node on the tree.
88. The developer clicks Update.
89. Verify that the application reset the Primitive Type of the Creation Date Time node to “Primitive” and the Primitive is reset back to “Token”. (Assertion #19.1)
90. The developer sets its Primitive Type to “Agency”.
91. He clicks Update.
92. Verify that the application reset the Primitive Type of the Creation Date Time node to “Primitive” and the Primitive is reset back to “Token”. (Assertion #19.1)
93. Verify that “string” and “integer” are not included in the Primitive drop down list. (Partially covering Assertion #19.2)
94. The developer logs out.
95. An end user logs in. Create a new code list, say oacl_ LanguageCodeExtension based on oacl_LanguageCode and publishes it.
96. The end user logs out. A developer logs in. He opens up a top-level BIE, which has a Language Code BBIE.
97. The developer enables and clicks on the Language Code node.
98. He sets the Primitive Type to “Code”.
99. Verify that only oacl_LanguageCode, clm56392A20081107_LanguageCode, and oacl_ LanguageCodeExtension are present in the dropdown list. (Assertion #19.3, #20)
100. The developer opens BIE7 for editing.
101. He expands the BIE7 tree and clicks on the node which has not been enabled as used.
102. Verify that the fields of node on the right pane are not editable. (Assertion #20)
103. The developer ensures that a few nodes in the same hierarchy are enabled (e.g., if the top-level BIE is a BOD, the developer enables Application Area, Sender, and Type Code underneath).
104. Verify that the fields of the unused nodes cannot be changed. (Assertion #21)
105. The developer opens BIE7 clicks the Hide unused checkbox.
106. Verify that only the nodes that are enabled/used are displayed when expanding the BIE7’s tree structure. (Assertion #22)
107. The developer clicks Hide unused checkbox.
108. Verify that at least a few of unused nodes of BIE7 are visible. (Assertion #22)
109. The developer makes a change. For instance, he enables the “System Environment Code”, change the “Business Term” field and clicks the Hide unused checkbox.
110. Verify that the changes has successfully recorder and they have not been lost. (Assertion #22)
111. The developer goes to Copy BIE page.
112. Verify that the BIEa is not displayed in the list. (Assertion #23)
113. He chooses a Business Context and in the next page chooses the BIE7.
114. Verify that the BIE is successfully copied (by checking using some nodes enabled in BIE7 are also enabled in the new BIE) and recorded by the application. (Assertion #24)
115. The developer goes to Copy BIE page.
116. Verify that the BIEb, BIEc, BIE1, and BIE2 are available for copying. (Assertion #25)
117. The developer logouts and the developer devx logins
118. He opens BIE0 for editing and changes it to the Candidate state.
119. Verify that the transfer ownership button is not available for BIE0 and BIE1. (Assertion #26, 27)
120. The developer opens BIE0. Change it back to the Editing state.
121. He clicks the transfer ownership button on BIE0.
122. Verify that there is no username of an end user available for selection.
123. He selects a username of another developer (e.g. devy).
124. Verify that the BIE’s ownership is transferred to the new user and there is no transfer button available for BIE0 on the BIE List page. (Assertion #26, 27)
125. The developer goes to the Create BIE page.
126. He enters the keyword “userb” to the search drop-down box of the “Updater” search field.
127. Verify that the user “userb” appears only. Also verify that “oagi”, “devx” and “usera” users do not appear. (Assertion #28)
128. He chooses a Business Context and goes to the second page where he can select a Top-Level Concept to create a BIE.
129. He enters the keyword “userb” to the search drop-down box of the “Updater” search field.
130. Verify that the user “userb” appears only. Also verify that “oagi”, “devx” and “usera” users do not appear. (Assertion #28)
131. The developer clears everything and he enters the search term “BOM Extension” into the Property Term field.
132. Verify that at least the “Revised BOM Component Extension” and the “Revised BOM Extension” are returned.  (Assertion #28)
133. He clears everything and he enters the search term “”BOM Extension”” into the Property Term field.
134. Verify that the “Revised BOM Extension” is returned and not the “Revised BOM Component Extension”.  (Assertion #28)
135. The developer clears everything and he enters the search term “Acknowledge Production” into the Property Term field that partially matches some ASCCPs’ Property Terms names.
136. Verify that at least the ASCCP Property Term “Acknowledge Production Order” is returned. (Assertion #28)
137. The developer enters the search term “AcknowledgeProduction” into the Module field that partially matches some Modules’ names.
138. Verify that at least the Module “ModelBODsAcknowledgeProductionOrder” is returned. (Assertion #28)
139. The developer enters the search keyword “cknowledgeProductionOrder Business Object Document is to” into the Definition field that partially matches some definitions of ASCCP.
140. Verify that at least the ASCCP Property Term “Acknowledge Production Order”. (Assertion #28)
141. The developer opens a BIE, say the BIE7, he selects “Code” as a “Primitive type” and he enters the keyword “Extension” into the drop-down search field.
142. Verify that the oacl_LanguageCode_Extension appears but not the clm56392A20081107_LanguageCode. (Assertion #28)
143. The developer goes to BIE List page.
144. He enters the keyword “userb” to the search drop-down box of the “Updater” search field.
145. Verify that the user “usberb” appears only. Also verify that “oagi”, “devx” and “usera” users do  not appear. (Assertion #29)
146. The developer clears everything and he enters the search term “BOM Extension” into the Property Term field.
147. Verify that at least the “Revised BOM Component Extension” and the “Revised BOM Extension” are returned.  (Assertion #29)
148. He clears everything and he enters the search term “”BOM Extension”” into the Property Term field.
149. Verify that the “Revised BOM Extension” is returned and not the “Revised BOM Component Extension”.  (Assertion #29)
150. He clears everything and he enters the search term “aster” that partially matches some BIEs’ names.
151. Verify that at least the BIE “Sync Project Master” is returned. (Assertion #29)
152. He enters the search term “initBC” in the “Business Context” search field.
153. Verify that at least the BIE “Sync Project Master” is returned. (Assertion #29).
154. He chooses "Editing” state to filter BIEs.
155. Verify that there is at least one BIE in Editing state and no BIE in Candidate or Published state (Assertion #29).
156. He chooses "Candidate” state to filter BIEs.
157. Verify that there is at least one BIE in Candidate state and no BIE in Editing or Candidate state (Assertion #29).
158. He chooses "Published” state to filter BIEs.
159. Verify that there is at least one BIE in Published state and no BIE in Editing or Candidate state (Assertion #29).
160. He clears everything and he chooses “oagis” user in the “Owner” selector field.
161. Verify that there is at least one BIE with the Oagi user as the owner but no BIEs with other owners (Assertion #29).
162. He clears everything and he chooses “oagis” user in the “Updater” selector field.
163. Verify that there is at least one BIE with the Oagi user as the updater but no BIEs with other updaters (Assertion #29).
164. The developer goes to Copy BIE page.
165. He enters the keyword “userb” to the search drop-down box of the “Updater” search field.
166. Verify that the user “userb” appears only. Also verify that “oagi”, “devx” and “usera” users do not appear. (Assertion #30)
167. The developer clears everything and he enters the search term “BOM Extension” into the Property Term field.
168. Verify that at least the “Revised BOM Component Extension” and the “Revised BOM Extension” are returned.  (Assertion #30)
169. He clears everything and he enters the search term “”BOM Extension”” into the Property Term field.
170. Verify that the “Revised BOM Extension” is returned and not the “Revised BOM Component Extension”.  (Assertion #30)
171. He clears everything and he enters the search term “redit” that partially matches some BIEs’ names.
172. Verify that at least the BIE “Show Credit” is returned. (Assertion #30)
173. The developer creates a new BIE using the Property Term “Tool Actual”.
174. He opens the BIE tree, expands Identifier node and the Identifier Set node.
175. Check that the Identifier node is not displayed again inside the Identifier Set and so there is no loop of the same-name node. (Assertion 31)
176. The developer goes to Copy BIE page, selects a random Business Context and then clicks next button. Afterwards, he counts the BIEs to check if they are the same as the index number displaying at the bottom right of the page. (Assertion #32)
177. The developer creates some business contexts.
178. The developer creates a new BIE, say BIE9, and during its creation he chooses multiple business contexts.
179. Verify that these business contexts are successfully assigned to the BIE9. (Assertion # 33)
180. He opens BIE BIE8 and adds some business contexts to it (e.g BusCon0, BusCon1).
181. Verify that the business contexts have successfully assigned to the BIE8. (Assertion #34)
182. The developer opens BIE8 and he tries to assign a business context already assigned (e.g. BusCon0)
183. Verify that the business context BusCon0 is not available for assignment. (Assertion #35)
184. The developer opens BIE8 and removes the BusCon0.
185. Verify that the no was successfully removed via BIE list, View/Edit and BIE expression page. Also verify that the others assigned business contexts was not removed. (Assertion #36)
186. The developer opens BIE8 and removes all business contexts.
187. Verify that there is at least one business process assigned and displayed in BIE list, View/Edit and BIE expression page. (Assertion #37)
188. The developer opens BIE8, enables some BBIEPs and BBIE_SC nodes that have an “Example” field (e.g. Action Code, Total Cost Amount, Unit Code), he adds some values and Updates the BIE.
189. Verify that the BIE has been successfully updated.  (Assertion #38)
190. The developer opens BIE8, enables a node that has Value Constraint field (e.g. Action Code). Afterwards, he selects the Fixed value as a value of that field, adds a value to its corresponding input field and clicks update.
191. Verify that he could not choose Default value as a value of the Constraint field and that the BIE has been successfully updated.  (Assertion #39)
192. The developer opens BIE8, enables a node that has Value Constraint field (e.g. Action Code). Afterwards, he selects the Default value as a value of that field, adds a value to its corresponding input field and clicks update.
193. Verify that he could not choose Fixed value as a value of the Constraint field and that the BIE has been successfully updated.  (Assertion #39)
194. The developer opens BIE9 and clicks on a node that has Min Cardinality 1 (e.g. Release Identifier)
195. Verify that it is enabled by default and that it cannot be disabled. (Assertion #40)
196. The developer expands the BIE tree and clicks a child node that has Min Cardinality 1 (e.g. Identifier of Document Identifier Set of Match Document Header)
197. Verify that the node is enabled by default and that it cannot be disabled. Also, verify that some of its parent nodes are disabled. (Assertion #40)
198. The developer visits the BIE List page, he selects a BIE (clicking the corresponding checkbox), goes to the next paginator pages and then returns back.
199. Verify that the checkbox of the selected BIE is checked. (Assertion #41)