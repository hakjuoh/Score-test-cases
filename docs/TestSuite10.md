# Test Suite 10

We did think about using the concept of project (which like a branch). In that case, users need to create a CC Release Project first. Users can create multiple CC Release Projects at the same time. Each release project is like a branch so the project has a snapshot from a release. This would allow users to create a bug fix release from any prior release. But this would mean we have to create a merging feature. Also, typically, OAGi does not go back and create a fix for prior release. So, we can say that the current tool design only allows linear management of core component releases.

If we do however let the user work on BIEs based on any prior release and user extension to those BIEs can be created within those releases. Then, it is sort of like a branch. And we would like to create a sort of a merge functionality. It is not a merge per se because it is more like an alignment, i.e., the core components (the standard) always win.

## Test Case 10.1

> Core component access

Pre-condition: A working branch is selected.
(As it is now) individual ASCC page is not provided.


### Test Assertion:

#### Test Assertion #1
The developer can see in the CC list page all CCs owned by any developer in any state.

#### Test Assertion #2
The developer can view and edit the details of a CC that is in WIP state and owned by him.

#### Test Assertion #3
The developer CAN view but CANNOT edit the details of a CC that is in WIP state and owned by another developer. However, he can add comments.

#### Test Assertion #4
The developer can view the details of a CC that is in Draft, Candidate, or Release Draft state and owned by any developer but he cannot make any change except adding comments.

#### Test Assertion #5
The developer can view the details of a Published CC owned by any developer but he cannot make any change except adding comments or make a new revision of the CC.

#### Test Assertion #6
There must not be any end user CC or User Extension Group CC listed in the Working branch.

#### Test Assertion #7
The developer can view details of a deleted CC owned by another developer.

#### Test Assertion #8
The developer cannot edit details of a deleted CC owned by him. He can add comments.

#### Test Assertion #9
The developer cannot edit details of a deleted CC owned by another developer. He can add comments.

#### Test Assertion #10
The developer can filter Core Components based on the branch.

#### Test Assertion #11
The developer can filter Core Components based on their Type.

#### Test Assertion #12
The developer can filter Core Components based on their State.

#### Test Assertion #13
The developer can filter Core Components based on their Updated Date.

#### Test Assertion #14
The developer can search for Core Components based only on their DEN, particularly when using the exact search with double quotes, only DEN containing exact match should return. For example, test this with “identifier group”, the result (of ACC search) shall be totally different from “identifiers group”.

#### Test Assertion #15
The developer can search for Core Components based only on their Definition, particularly when using the exact search with double quotes, only definition containing exact match should return. For example, test this with “Actual Ledger”, the result (of ASCCP search) shall be totally different from “Ledger Actual”.

#### Test Assertion #16
The developer can search for Core Components based only on their Module.

#### Test Assertion #17
The developer can search for Core Components based only on their Component Type.

#### Test Assertion #18
The developer can short Core Component based on the Den column.

#### Test Assertion #19
The developer can move states of several CCs in one shot on the view/edit CC page. Test for:

##### Test Assertion #19.a
Changing state from WIP to Draft
##### Test Assertion #19.b
Changing state from Draft to WIP
##### Test Assertion #19.c
Changing state from Draft to Candidate
##### Test Assertion #19.d
Transfer the ownership
##### Test Assertion #19.e
Deleting.

#### Test Assertion #20
The developer can open a CC and find the usages of its nodes (i.e., ACC, ASCCP or BCCP) by invoking the function “Where Used” of the context menu of a particular node. In the returned dialog, he can view where the CC wherein the selected CC is used. Check the usages for ACC, ASCCP and BCCP nodes.

##### Test Assertion #20.a
If an ACC is selected to view wherein it is used, then the ACCs which are based on this ACC either directly or indirectly should be listed in the returned dialog.

### Test Step Pre-condition:

1. There are the following core components:
2. ACCxw, ASCCPxw, BCCPxw created by the developer devx and they are in WIP state
3. ACCxd, ASCCPxd, BCCPxd created by the developer devx and they are in Draft state.
4. ACCxc, ASCCPxc, BCCPxc created by the developer devx and they are in Candidate state.
5. ACCxdel, ASCCPxdel, BCCPxdel created by the developer and be deleted.
6. ACCow, ASCCPow, BCCPow created by the developer oagis and they are in WIP state.
7. ACCod, ASCCPod, BCCPod created by the developer oagis and they are in Draft state.
8. ACCoc, ASCCPoc, BCCPoc created by the developer oagis and they are is Candidate state.
9. …to be expanded when the release is done

### Test Step:

1. The oagis developer logs into Score.
2. The visits the CC page.
3. Verify that he can view in the returned list all the CCs mentioned in the precondition section. (Assertion [#1](#test-assertion-1))
4. The developer clicks on the ACC0w.
5. Verify that he can view and edit it. (Assertion [#2](#test-assertion-2))
6. The developer goes back to the CC list page and clicks on ASCCP0w.
7. Verify that he can view and edit it. (Assertion [#2](#test-assertion-2))
8. The developer goes back to the CC list page and clicks on BCCP0w.
9. Verify that he can view and edit it. (Assertion [#2](#test-assertion-2))
10. The developer goes back to the CC list page and clicks on ACCxw.
11. Verify that he can view it, but he cannot edit it.  (Assertion [#3](#test-assertion-3))
12. He clicks the comment button.
13. Verify that he can view the comments, but he cannot add one. (Assertion [#3](#test-assertion-3))
14. The developer goes back to the CC list page and clicks on ASCCPxw.
15. Verify that he can view it, but he cannot edit it. (Assertion [#3](#test-assertion-3))
16. He clicks the comment button.
17. Verify that he can view the comments, but he cannot add one. (Assertion [#3](#test-assertion-3))
18. The developer goes back to the CC list page and clicks on BCCPxw.
19. Verify that he can view it, but he cannot edit it. (Assertion [#3](#test-assertion-3))
20. He clicks the comment button.
21. Verify that he can view the comments, but he cannot add one. (Assertion [#3](#test-assertion-3))
22. The developer goes back to the CC list page and clicks on ACCxd.
23. The developer makes a comment to the CC.
24. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
25. The developer goes back to the CC list page and clicks on ASCCPxd.
26. The developer makes a comment to the CC.
27. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
28. The developer goes back to the CC list page and clicks on BCCPxd.
29. The developer makes a comment to the CC.
30. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
31. The developer goes back to the CC list page and clicks on ACCxc.
32. The developer makes a comment to the CC.
33. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
34. The developer goes back to the CC list page and clicks on ASCCPxc.
35. The developer makes a comment to the CC.
36. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
37. The developer goes back to the CC list page and clicks on BCCPxc.
38. The developer makes a comment to the CC.
39. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
40. ……to be expanded after release management.
41. The developer visits the CC list page and clicks on ACCxdel.
42. Verify that he can view its details. (Assertion [#7](#test-assertion-7))
43. The developer visits the CC list page and clicks on ASCCxdel.
44. Verify that he can view its details. (Assertion [#7](#test-assertion-7))
45. The developer visits the CC list page and clicks on BCCPxdel.
46. Verify that he can view its details. (Assertion [#7](#test-assertion-7))

## Test Case 10.2

> Creating a brand-new developer ACC

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
On the CC list page where a working branch is selected, the developer can create a brand-new ACC with the following default values – Object Class Term = “Object Class Term”; DEN = [Object Class Term] + “. Details” and disabled; Component Type = “Semantics”; Abstract = false; Definition = blank; Definition Source= blank; Deprecated = false (and locked); Namespace = null, Comments = empty. The brand-new ACC must not have any release assigned yet, i.e., it must not appear in any release branch except the working branch. It has a revision number 1. All fields are required and cannot be blank except Definition, Definition Source, and Comments. Only the following Component Type can be selected Base, Semantics, Semantic_Group.

#### Test Assertion #2
The developer cannot create a brand-new developer ACC when a release branch is selected.

### Test Step Pre-condition:



### Test Step:

1. An OAGi developer logs into the system.
2. He visits CC page and creates a new ACC.
3. Verify that the default values of the ACC are those mentioned in Assertion #1
4. The developer visits CC List page and selects a release branch.
5. Verify that the new ACC is not displayed. (Assertion [#1](#test-assertion-1))
6. Verify that there is no “Create ACC” button. (Assertion [#2](#test-assertion-2))

## Test Case 10.3

> Editing a brand-new developer ACC

Pre-condition: The brand-new ACC is created by the developer and is in the WIP state. The developer accesses these functionalities by opening the brand-new ACC from the CC list page or after creating a brand-new ACC according to Test Assertion #1 of the Test Case 10.2.


### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the ACC and save changes with the following business rules.

##### Test Assertion #1.a
If the Component Type is base, Abstract shall be true and disabled.
##### Test Assertion #1.b
Abstract can only be true when the Component Type is base or Semantics.If it is Semantics Abstract should be enabled.
##### Test Assertion #1.c
Object Class Term, Component Type, Namespace, and Abstract are required.  There should be a drop-down list to select a namespace. Only Namespace that is a standard namespace shall be allowed. The following Component Type shall be disabled or hidden – Extension, User Extension Group, Embedded, OAGIS 10 Nouns, OAGIS 10 BODs.
##### Test Assertion #1.d
Deprecated must be false and locked b/c revision is 1.
##### Test Assertion #1.e
A warning should be given when the Definition is empty.
##### Test Assertion #1.f
If Object Class Term of the ACC change and there is one or more ASCCP depending on it, DEN of those ASCCP shall be updated accordingly, (Note: This should affect ASCCPs that are in revision 1 only.)
##### Test Assertion #1.g
 Only the following Component Type can be selected Base, Semantics, and Semantic_Group.

#### Test Assertion #2
When the Component_Type is Semantics, the developer can invoke a function/macro (maybe via a button next to the Component Type field) “Create Extension Component” to automatically create the extension component for the ACC. The application shall check whether there is already an association to an ASCCP whose property term is “Extension”. If so, notify the user “The ACC already has an extension component.”, and exit. If so, notify the user “The ACC already has an extension component.”, and exit. If not, create an association to the ASCCP as defined below and add, to the ACC, the association to the Extension ASCCP.

##### Test Assertion #2.a
The Extension ACC shall be created with the All Extension ACC as base. It shall have the Object Class Term = [Object Class Term of the current ACC] + “Extension”, the Component Type = Extension, and the namespace and owner is the same as that of the current ACC.
##### Test Assertion #2.b
The Extension ASCCP shall be created using the above Extension ACC. Its Property Term = “Extension”.
##### Test Assertion #2.c
The ASCC shall have zero to unbounded cardinality.
##### Test Assertion #2.d
The developer cannot create an OAGIS Extension if the ACC does not have a namespace (the ACC does not have namespace immediately after it is created).

#### Test Assertion #3
The developer can Exclude SCs or not from the Searching Field by checking or unchecking the “Exclude SCs” checkbox accordingly.

##### Test Assertion #3.a
If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
##### Test Assertion #3.b
If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field

### Test Step Pre-condition:

1. There is an ACC, say ACC103a, which is a brand new ACC and it is in WIP state
2. There is an ACC, say ASCCP103a, which is a brand new ASCCP, uses ACC103a and it is in WIP state
3. The working branch is selected

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the ACC103a.
3. He sets the Component Type to base.
4. Verify that the Abstract is True and checkbox is disabled. (Assertion [#1.a](#test-assertion-1a))
5. He sets the Component Type to Semantics.
6. Verify that he can set Abstract (the checkbox is enabled). (Assertion [#1.b](#test-assertion-1b))
7. He sets the Component Type to Extension.
8. Verify that he cannot set Abstract (the checkbox is disabled) and that the Abstract is False. (Assertion [#1.b](#test-assertion-1b))
9. He sets the Component Type to Semantic Group.
10. Verify that he cannot set Abstract (the checkbox is disabled) and that the Abstract is False. (Assertion [#1.b](#test-assertion-1b))
11. The developer sets the Namespace to a valid one (e.g., http://www.openapplications.org/oagis/10) and updates the ACC.
12. Verify that the ACC has been successfully updated. (Assertion [#1.c](#test-assertion-1c))
13. The developer sets the Namespace to Null (e.g., “-“) and updates the ACC.
14. Verify that the Update button is disabled or that there is no null mat-select option. (Assertion [#1.c](#test-assertion-1c))
15. The developer clicks on the Component Type selector.
16. Verify that the User Extension Group, Embedded, OAGIS 10 Nouns, OAGIS 10 BODs are disabled. (Assertion [#1.c](#test-assertion-1c))
17. The developer tries to change Deprecated checkbox.
18. Verify that the Deprecated checkbox is disabled. (Assertion [#1.d](#test-assertion-1d))
19. The developer leaves the Definition field empty and updates the ACC103a.
20. Verify that a warning message is returned. (Assertion [#1.e](#test-assertion-1e))
21. The developer changes the Object Class Term of the ACC103a.
22. Verify that the DEN of the ASCCP103a has been changed accordingly. (Assertion [#1.f](#test-assertion-1f))

## Test Case 10.4

> Editing associations of a brand-new developer ACC

Pre-condition: The brand-new ACC is created by the developer and is in the WIP state. The developer accesses these functionalities by opening the brand-new ACC from the CC list page or after creating a brand-new ACC according to Test Assertion #1 of the Test Case 10.2.


### Test Assertion:

#### Test Assertion #1
The developer can append a developer ASCCP to the ACC (maybe by right-clicking the ACC) that results in an association to a developer ASCCP. The default value of the new ASCC shall be as follows: Min = 0, Max = “unbounded”, Deprecated = false and disabled, Definition=empty, Definition Source=empty.

##### Test Assertion #1.a
The developer ASCCP can be in any state.
##### Test Assertion #1.b
A warning shall be given if the ASCCP is deprecated.
##### Test Assertion #1.c
The ACC shall not already contain an ASCCP or BCCP with the same property term whether in itself or within its based ACC. (maybe, the ASCCP with the same property should not appear in the list of the dialog used to append ASCCPs. Note that there may be multiple ASCCPs with the same property term even in the same release – this situation occurs with the Data Area ASCCP. But maybe easier to test if giving error after a problematic ASCCP is selected). The test should account for the cases of group ASCCP – 1) there is a group in the based ACC, the developer appends a non-group ASSCP that has the same property term as a property in the group of the based ACC; 2) there is a group in the based ACC, the developer appends a group ASCCP that has a child with the same property term as a property in the group of the based ACC; 3) The ACC has a group ASCCP and the developer appends an ASCCP that has the same property term as a property in the group; 4) The ACC has a group ASCCP and the developer appends another group ASCCP that cause the two groups to have some duplicate property terms; 5) same as (1) to (4) but groups have a cascaded a group.
##### Test Assertion #1.d
The resulting ASCC shall be in the WIP state.
##### Test Assertion #1.e
If the ASCCP is not reusable, check that there is no ASCC already using it. Also test for when non-reusable ASCCP has been deleted while still having an association and the developer still try to user the ASCCP in another association.
##### Test Assertion #1.f
No end user ASCCP can be selected.

#### Test Assertion #2
The developer can right-click on any associations and Insert an ASCCP before or after. The rest of the behavior is the same as test assertion #1.

#### Test Assertion #3
The developer can update the following fields of its new ASCC (rev = 1); Min, Max, Definition, Definition Source. I.e., he cannot update the details of the ASCCP. The following business rules are applied:

##### Test Assertion #3.a
Min >= 0
##### Test Assertion #3.b
Max >= -1 and (Max >= Min when Max != -1)
##### Test Assertion #3.c
The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
##### Test Assertion #3.d
Min, Max, and Deprecated are required.
##### Test Assertion #3.e
A warning should be given when the Definition is empty.
##### Test Assertion #3.f
Deprecated must be false and locked (because it is a new association, it shouldn’t be deprecated).

#### Test Assertion #4
The developer can append a developer BCCP to an ACC (maybe by right clicking the ACC) that results in an association to the developer BCCP. The default value of the new BCC shall be as follows: Min=0, Max = “unbounded”, Deprecated = false and disabled, Entity Type = Element, Value Constraint= None (Default and Fixed value should be empty), Definition = empty, Definition Source = empty.

##### Test Assertion #4.a
The developer BCCP can be in any state.
##### Test Assertion #4.b
A warning shall be given if the BCCP is deprecated.
##### Test Assertion #4.c
The ACC shall not already contain a BCCP or ASCCP with the same property term whether in itself or within its based ACC. See TA 1.3 for different testing situations to cover.
##### Test Assertion #4.d
The resulting BCC shall be in the WIP state.

#### Test Assertion #5
No end user BCCP can be selected.The developer can right-click on any associations and choose insert a BCCP before or after it. The rest of the behavior is the same as test assertion #4.

#### Test Assertion #6
The developer can edit the following info of a BCC - Min, Max, Entity Type, Default or Fixed Value, Definition, and Definition Source. He cannot update the BCCP information. The following business rules apply:

##### Test Assertion #6.a
Min >= 0
##### Test Assertion #6.b
Max >= -1 and (Max >= Min when Max != -1)
##### Test Assertion #6.c
The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
##### Test Assertion #6.d
All fields except Definition and Definition Source are required. However, a warning should be given when the Definition is empty.
##### Test Assertion #6.e
Deprecated must be false (because it is a new association, it shouldn’t be deprecated).
##### Test Assertion #6.f
The Default and Fixed value shall be disabled and cleared of value if the Entity Type is Element. The system shall warn the user that the Default and Fixed Value will be cleared if changing entity type to Element. If enabled, the Default and Fixed value shall be mutually exclusive.
##### Test Assertion #6.g
The Attribute Entity Type can be applied only if the BCCP has no SC or all SCs have max cardinality zero.
##### Test Assertion #6.h
If the Entity Type is changed from Element to Attribute the Min Cardinality should be changed to 0 and the Max Cardinality to 1.

#### Test Assertion #7
The developer can change (move up or down) the sequence of an association to an ASCCP. It would be good to be able to drag-n-drop instead of moving up or down.

#### Test Assertion #8
The developer can change (move up or down) the sequence of an association to a BCCP. It would be good to be able to drag-n-drop instead of moving up or down.

#### Test Assertion #9
The developer can remove an association (ASCC or BCC), there must be a confirmation dialog box though. (In that case, the association information is stored in the history record).

#### Test Assertion #10
The developer can assign another developer ACC belonging to the working branch as a base of this ACC.

##### Test Assertion #10.a
The base ACC can be in any state.
##### Test Assertion #10.b
If the chosen base ACC is deprecated, a warning shall be given.
##### Test Assertion #10.c
The base ACC shall only be Base or Semantics component type (not be a Group, User Extension Group, or Embedded component type, etc.).
##### Test Assertion #10.d
The developer cannot change the fields of the base ACC.
##### Test Assertion #10.e
End user ACC cannot be selected as a base.
##### Test Assertion #10.f
Duplicate property term needs to be checked. See TA 1.3 for different testing situations to cover. In addition, the case of multiple layers of inheritance needs to be taken into account.

#### Test Assertion #11
The developer can remove the based ACC when one exists.

#### Test Assertion #12
The developer can transfer the ownership of an ACC, ONLY when it is in WIP states and owned by him, to ONLY another developer. In that case the ownership of the associations (ASCC and BCC) are transferred as well.

#### Test Assertion #13
The developer can refactor an ASCCP to base ACC providing that the base ACC is in WIP state, owned by the developer and there is no association to the refactoring ASCCP within base ACC hierarchy neither there is an association to the refactoring ASCCP within the ACCs that have the base ACC within their hierarchy.

#### Test Assertion #14
The developer cannot refactor an ASCCP to base ACC if

##### Test Assertion #14.a
The base ACC is in Draft state
##### Test Assertion #14.b
The base ACC is in Candidate state
##### Test Assertion #14.c
The base ACC is in Published state
##### Test Assertion #14.d
The base ACC in Deleted
##### Test Assertion #14.e
The base ACC is owned by another developer regardless of the state

#### Test Assertion #15
The developer cannot refactor an ASCCP to base ACC if the latter already contains this ASCCP either directly on indirectly in its hierarchy. When the developer selects the base ACC, he should be able to validate the choice. This means that Score should display all ACCs that the developer should take some action. After the developer takes that actions, Score deletes the associations to the ASCCPs that are same as the refactoring ASCCP (duplicate ASCCPs) and moves the refactoring ASCCP to the selected base ACC. Check for:

##### Test Assertion #15.a
Moving an ACC to WIP state
##### Test Assertion #15.b
Take the ownership of an ACC and move it to WIP state
##### Test Assertion #15.c
which are not in WIP state and those not in WIP state that also contain the refactoring

#### Test Assertion #16
The developer cannot refactor an ASCCP to a selected base ACC if the ASCCP already exists as a property in a group ACC used in an association of under an ACC that exists in a hierarchy of the selected base ACC. In this case the developer should ungroup the group ACC so that he can refactor the ASCCP to the base ACC.

#### Test Assertion #17
The developer can cancel the revision of the Editing ACC. Doing so, Score restores the association to the refactored ASCPP.

#### Test Assertion #18
The developer can cancel the revision of the base ACC where an ASCCP was moved. Doing so, Score deletes the association to the ASCCP.

#### Test Assertion #19
The developer can cancel the revision of an ACC that had the base ACC as its based and also it had an association to the ASCCP that the developer refactored (this association was deleted because of the refactoring). Doing so, Score restores the association to the refactored ASCPP.

#### Test Assertion #20
The developer can refactor an BCCP to base ACC providing that the base ACC is in WIP state, owned by the developer and there is no association to the refactoring BCCP within base ACC hierarchy neither there is an association to the refactoring BCCP within the ACCs that have the base ACC within their hierarchy.

#### Test Assertion #21
The developer cannot refactor an BCCP to base ACC if

##### Test Assertion #21.a
The base ACC is in Draft state
##### Test Assertion #21.b
The base ACC is in Candidate state
##### Test Assertion #21.c
The base ACC is in Published state
##### Test Assertion #21.d
The base ACC in Deleted
##### Test Assertion #21.e
The base ACC is owned by another developer regardless of the state

#### Test Assertion #22
The developer cannot refactor an BCCP to base ACC if the latter already contains this BCCP either directly on indirectly in its hierarchy. When the developer selects the base ACC, he should be able to validate the choice. This means that Score should display all ACCs with some issues, namely the ACCs that contain the refactoring BCCP already of the base ACC that contain the BCCP. If the developer  refactors the BCCP to the selected base ACC, the BCCPs that exists in the hierarchy are deleted and the new BCCP is moved to the base ACC.

#### Test Assertion #23
The developer cannot refactor an BCCP to base ACC if the BCCP already exists as a property in a group ACC which exists under the base ACC.

#### Test Assertion #24
The developer can cancel the revision of the Editing ACC. Doing so, Score restores the association to the refactored BCCP.

#### Test Assertion #25
The developer can cancel the revision of the base ACC where an BCCP was moved. Doing so, Score deletes the association to the BCCP.

#### Test Assertion #26
The developer can cancel the revision of an ACC that had the base ACC as its based and also it had an association to the BCCP that the developer refactored (this association was deleted because of the refactoring). Doing so, Score restores the association to the refactored BCCP.

### Test Step Pre-condition:

1. There are the following core components:
2. ACC104ow, ACC104owassoc created by the developer conducing the steps and they are in WIP state
3. ACC104odassoc, ACC104ocassoc created by the developer conducing the steps and they are in Draft and Candidate state respectively
4. ASCCP104ow, BCCP104ow created by the developer conducing the steps and they are in WIP state
5. ASCCP104od, BCCP104od created by the developer conducing the steps and they are in Draft state
6. ASCCP104oc, BCCP104oc created by the developer conducing the steps and they are in Candidate state
7. ASCCP104devxw, BCCP104devxw created by the developer devx and they are in WIP state
8. ASCCP104devxd, BCCP104devxd created by the developer devx and they are in Draft state
9. ASCCP104devxc, BCCP104devxc created by the developer devx and they are in Candidate state
10. ASCCP104odel, BCCP104odel created by the developer conducting the steps and they are in Deleted state.
11. ASCCP104odeprec, BCCP104odeprec created by the developer conducting the steps and they are Deprecated.
12. ACCoc, ASCCPoc, BCCPoc created by the developer oagis and they are is Candidate state

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the ACC103a.
3. He sets the Component Type to base.
4. Verify that the Abstract is True and checkbox is disabled. (Assertion [#1.a](#test-assertion-1a))
5. He sets the Component Type to Semantics.
6. Verify that he can set Abstract (the checkbox is enabled). (Assertion [#1.b](#test-assertion-1b))
7. He sets the Component Type to Extension.
8. Verify that he cannot set Abstract (the checkbox is disabled) and that the Abstract is False. (Assertion [#1.b](#test-assertion-1b))
9. He sets the Component Type to Semantic Group.
10. Verify that he cannot set Abstract (the checkbox is disabled) and that the Abstract is False. (Assertion [#1.b](#test-assertion-1b))
11. The developer sets the Namespace to a valid one (e.g., http://www.openapplications.org/oagis/10) and updates the ACC.
12. Verify that the ACC has been successfully updated. (Assertion [#1.c](#test-assertion-1c))
13. The developer sets the Namespace to Null (e.g., “-“) and updates the ACC.
14. Verify that the Update button is disabled or that there is no null mat-select option. (Assertion [#1.c](#test-assertion-1c))
15. The developer clicks on the Component Type selector.
16. Verify that the User Extension Group, Embedded, OAGIS 10 Nouns, OAGIS 10 BODs are disabled. (Assertion [#1.c](#test-assertion-1c))
17. The developer tries to change Deprecated checkbox.
18. Verify that the Deprecated checkbox is disabled. (Assertion [#1.d](#test-assertion-1d))
19. The developer leaves the Definition field empty and updates the ACC103a.
20. Verify that a warning message is returned. (Assertion [#1.e](#test-assertion-1e))
21. The developer changes the Object Class Term of the ACC103a.
22. Verify that the DEN of the ASCCP103a has been changed accordingly. (Assertion [#1.f](#test-assertion-1f))

## Test Case 10.5

> Creating a new revision of a developer ACC

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
On the CC Detail page of the working branch, the developer can create a new revision of an ACC that is in Published state regardless of the current owner. The result is that the working branch has that ACC and its associations with an incremental revision number that is in the WIP state.  Its detail attributes are initially the same as those of the previous revision.

#### Test Assertion #2
A new revision CANNOT be made on an ACC in non-Published state.

### Test Step Pre-condition:

1. There is the ACC105a (e.g, OAGIS10 Nouns. Details) that is in Published Release state.

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the ACC105a and creates a new revision.
3. Verify that the fields are the same as those of the previous revision. (Assertion [#1](#test-assertion-1))
4. Verify that a new revision has been created. (e.g., by visiting the CC list page and verifying that the revision is greater than 1) (Assertion [#1](#test-assertion-1))

## Test Case 10.6

> Editing a revision of a developer ACC

Pre-condition: The ACC under test has revision number greater than 1 and is in WIP state.


### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the ACC and save changes with the following business rules.

##### Test Assertion #1.a
Component Type cannot be changed.
##### Test Assertion #1.b
Abstract can only be changed from True to False, except when the Component Type is base where it should be locked as True.
##### Test Assertion #1.c
Object Class Term and Namespace cannot be changed.
##### Test Assertion #1.d
If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement ACC that is not already deprecated in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI. When the Replaced By field has a value, it shall display the ACC’s Object Class Term and GUID.
##### Test Assertion #1.e
Definition and Definition Source can be changed. However, a warning should be given when the Definition is empty.

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
3. Verify that the Component Type is the same with the previous revision and that it cannot be changed. (Assertion [#1.a](#test-assertion-1a))
4. He opens the “Application Area Base. Details” and creates a new revision.
5. Verify that the Component Type is “Base (Abstract)” and that the Abstract field is False and cannot be changed. (Assertion [#1.b](#test-assertion-1b))
6. He opens the “Business Object Document. Details” and creates a new revision.
7. Verify that the Component Type is “Semantics” and that the Abstract field is False and cannot be changed. (Assertion [#1.b](#test-assertion-1b))
8. He opens the “Change Status Extension. Details” and creates a new revision.
9. Verify that the Component Type is “Extension” and that the Abstract field is False and cannot be changed. (Assertion [#1.b](#test-assertion-1b))
10. He opens the “Container Instance Identifiers Group. Details” and creates a new revision.
11. Verify that the Component Type is “Semantic Group” and that the Abstract field is False and cannot be changed. (Assertion [#1.b](#test-assertion-1b))
12. He opens the “Document Reference Base. Details” and creates a new revision.
13. Verify that the Component Type is “Base (Abstract)” and that the Abstract field is True and cannot be changed. (Assertion [#1.b](#test-assertion-1b))
14. He opens the “Currency Exchange ABIE. Details” and creates a new revision.
15. Verify that the Component Type is “Semantics” and that the Abstract field is True and it can be changed. (Assertion [#1.b](#test-assertion-1b))
16. The developer changes Abstract to False and Updates the CC.
17. Verify that the CC has been successfully updated. (Assertion [#1.b](#test-assertion-1b))
18. The developer opens the ACC106a.
19. Verify that the Object Class Term field is disabled. (Assertion [#1.c](#test-assertion-1c))
20. Verify that the Deprecated field is enabled. (Assertion [#1.d](#test-assertion-1d))
21. …..
22. The developer changes the Definition Source and the Definition field and Updates the ACC106a
23. Verify that the ACC106a has been updated. (Assertion [#1.e](#test-assertion-1e))
24. The developer clears the Definition field and updates the ACC106a
25. Verify that a confirmation message saying that the definition is empty has been returned. (Assertion [#1.e](#test-assertion-1e))
26. The developer confirms its intentions to leave the Definition field blank.
27. Verify that the ACC106a has been updated. (Assertion [#1.e](#test-assertion-1e))

## Test Case 10.7

> Editing associations of a revision of a developer ACC

Pre-condition: The ACC revision (> 1) is created by the developer and is in the WIP state. The developer accesses these functionalities by opening an ACC revision (> 1) from the CC list page or after creating a ACC revision according to Test Assertion #1 of the Test Case 10.5.
Note: Association revision number of a new association changes to the same as ACC revision number when the ACC enters the published state.


### Test Assertion:

#### Test Assertion #1
The developer can append a developer ASCCP to an ACC that results in an association to the developer ASCCP. The default value of the new ASCC shall be as follows: Min = 0, Max = “unbounded”, Deprecated = false and disabled, Definition=empty, Definition Source = empty.

##### Test Assertion #1.a
The developer ASCCP can be in any state.
##### Test Assertion #1.b
A warning shall be given if the ASCCP is deprecated.
##### Test Assertion #1.c
The ACC shall not already contain an ASCCP or BCCP with the same property term whether in itself or within its based ACC. The ASCCP should not appear in the list of the dialog used to append ASCCPs or return an error after selection of violating BCCP or ASCCP. See TA 1.3 in Test Case 10.4 for different testing situations to cover.
##### Test Assertion #1.d
The resulting ASCC shall be in the WIP state.
##### Test Assertion #1.e
If the ASCCP is not reusable, check that there is no ASCC already using it. If there is an ASCC already using the ASCCP, the system shall report that the ASCCP is not reusable and that it is already used.
##### Test Assertion #1.f
End user ASCCPs cannot be appended

#### Test Assertion #2
On a particular association, the developer can insert an ASCCP before or after it. The rest of the behavior is the same as test assertion #1.

#### Test Assertion #3
The developer can update the following fields of its new ASCC (rev = 1); Min, Max, Definition, Definition Source. I.e., he cannot update the details of the ASCCP. The following business rules are applied:

##### Test Assertion #3.a
Min >= 0
##### Test Assertion #3.b
Max >= -1 and (Max >= Min when Max != -1)
##### Test Assertion #3.c
The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
##### Test Assertion #3.d
Min, Max, and Deprecated are required.
##### Test Assertion #3.e
A warning should be given when the Definition is empty.
##### Test Assertion #3.f
Deprecated must be false and locked (because it is a new association, it shouldn’t be deprecated).

#### Test Assertion #4
The developer can edit the information of existing ASCC (ASCC whose revision > 1) following these rules.

##### Test Assertion #4.a
0 <= Min <= PreviousMin
##### Test Assertion #4.b
If Previous-Max = -1, it cannot be changed; otherwise, Max = -1 or Max >= Previous-Max
##### Test Assertion #4.c
If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement ASCC or BCC (filtered out the deprecated ones) within the ACC from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
##### Test Assertion #4.d
A warning should be given when the Definition is empty.

#### Test Assertion #5
The developer can append a developer BCCP to an ACC that results in an association to the developer BCCP. The default value of the new BCC shall be as follows: Min=0, Max = “unbounded”, Deprecated = false and disabled, Entity Type = Element, Value Constraint= None (Default and Fixed value should be empty), Definition = empty, Definition Source = empty.

##### Test Assertion #5.a
The developer BCCP can be in any state.
##### Test Assertion #5.b
A warning shall be given if the BCCP is deprecated.
##### Test Assertion #5.c
The ACC shall not already contain an ASCCP or BCCP with the same property term whether in itself or within its based ACC. See TA 1.3 in Test Case 10.4 for different testing situations to cover.
##### Test Assertion #5.d
The resulting BCC shall be in the WIP state.
##### Test Assertion #5.e
End user BCCP cannot be appended.

#### Test Assertion #6
On a particular association and the developer can insert a BCCP before after it”. The rest of the behavior is the same as test assertion #5.

#### Test Assertion #7
The developer can edit the following info of the new BCC - Min, Max, Entity Type, Default or Fixed Value, Definition, and Definition Source. He cannot update the BCCP information. The following business rules apply:

##### Test Assertion #7.a
Min >= 0
##### Test Assertion #7.b
Max >= -1 and (Max >= Min when Max != -1)
##### Test Assertion #7.c
The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
##### Test Assertion #7.d
All fields except Definition and Definition Source are required. However, a warning should be given when the Definition is empty.
##### Test Assertion #7.e
Deprecated must be false (because it is a new association, it shouldn’t be deprecated).
##### Test Assertion #7.f
The Default and Fixed value shall be disabled and cleared of value if the Entity Type is Element. The system shall warn the user that the Default and Fixed Value will be cleared if changing entity type to Element. If enabled, the Default and Fixed value shall be mutually exclusive.
##### Test Assertion #7.g
If the Entity Type is changed from Element to Attribute the Min Cardinality should be changed to 0 and the Max Cardinality to 1.

#### Test Assertion #8
The developer can edit the following information of existing BCC (BCC whose revision >1).

##### Test Assertion #8.a
0 <= Min <= PreviousMin
##### Test Assertion #8.b
If Previous-Max = -1, it cannot be changed; otherwise, Max = -1 or Max >= Previous-Max
##### Test Assertion #8.c
If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement ASCC or BCC (filtered out the deprecated ones) within the ACC from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
##### Test Assertion #8.d
A warning should be given when the Definition is empty.
##### Test Assertion #8.e
Entity Type cannot be changed.
##### Test Assertion #8.f
If Entity Type is Attribute, Default and Fixed Value can be changed but mutually exclusive. If Entity Type is Element, Default and Fixed Value must be disabled. The Attribute Entity Type can be applied only if the BCCP has no SC or all SCs have max cardinality zero.

#### Test Assertion #9
The developer can change (move up or down) the sequence of the brand-new and existing association to an ASCCP. It would be good to be able to drag-n-drop instead of moving up or down. Existing associations cannot be moved.

#### Test Assertion #10
The developer can change (move up or down) the sequence of the brand-new and existing association to a BCCP. It would be good to be able to drag-n-drop instead of moving up or down. Existing associations cannot be moved.

#### Test Assertion #11
The developer can remove an existing new association (ASCC or BCC) added in this revision (new association added during this revision should still have revision #1), there must be a confirmation dialog box though. However, an association cannot be removed if it is used as a replacement of a deprecated association. Information about the removed association is kept in the history record. The developer can also remove an association added to a previous revision. There should also be a confirmation dialog. If the developer cancel the revision, the removed associations should be restored.

#### Test Assertion #12
The developer can assign another developer ACC belonging to the working branch as a base of this ACC, both in the case where a based ACC does and does not already exist in the previous revision.

##### Test Assertion #12.a
The base ACC can be in any state.
##### Test Assertion #12.b
If the chosen base ACC is deprecated, a warning shall be given.
##### Test Assertion #12.c
The base ACC shall not be a Group, User Extension Group, or Embedded component type.
##### Test Assertion #12.d
The developer cannot change the fields of the base ACC.
##### Test Assertion #12.e
The base ACC should not contain an ASCCP or a BCCP with the same property term as that already in the ACC itself (property uniqueness).
##### Test Assertion #12.f
Duplicate property term needs to be checked. See TA 1.3 for different testing situations to cover. In addition, multiple layers of inheritance need to be taken into account.

#### Test Assertion #13
The developer can remove the based ACC when one exists in the previous revision.

#### Test Assertion #14
The developer can transfer the ownership of an ACC, which is in WIP states and he owns, to another developer. In that case the ownership of the associations (ASCC and BCC) are transferred as well.

#### Test Assertion #15
The developer can cancel the revision. In this case, the system rollbacks all changes and additions to the ACC including its children associations and based ACC back to the previous revision. Information about those cancelled changes are in the history record.

#### Test Assertion #16
The developer can move an existing association (i.e., ASCCP, BCCP) of the revised ACC to its base ACC (including the base ACC of its base ACC as so fourth - For example if the revised ACC is based on ACC1 that is based on ACC2 that is based on ACC3, the developer the move the association to any of these ACCs). The base ACC has to be in WIP state while there must not be any BIE using the revised ACC or the base ACC.

### Test Step Pre-condition:



### Test Step:

## Test Case 10.8

> Developer ACC state management

Pre-condition: The user is on the ACC detail page, which he owns.
All these state changes need a confirmation dialog box with slightly different messages.


### Test Assertion:

#### Test Assertion #1
The developer can change the ACC state from WIP to Draft state. The system shall then change the state of its children associations that are also in the WIP state to the Draft state. There is no need to check the state of the dependencies (we will ensure that everything is consistently in the Candidate state at the release time). (Note that I change the rule about viewing details of CC in WIP state that the detail can be viewed by any user so the user should be able to expand the tree of the ACC).

#### Test Assertion #2
The developer can change the ACC state from Draft to Candidate. The system shall then change the state of its children associations that are also in the Draft state to the Candidate state.

#### Test Assertion #3
The developer can retract a candidate ACC. This action put the ACC and all of its association back to the WIP state.

#### Test Assertion #4
The developer can change the ACC state from Draft back to WIP. The system shall then change the state of its children associations also back to WIP.

### Test Step Pre-condition:

1. The following CCs should exist:
2. There are the ACC108a, ASCCP108a and BCCP108a created by the developer of the test case and they are in WIP state.

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the ACC108a and clicks Draft button.
3. The developer confirms its intention in the returned message.
4. Verify that the ACC108a is in Draft state. (Assertion [#1](#test-assertion-1))
5. He opens the ASCCP108a and clicks Draft button.
6. The developer confirms its intention in the returned message.
7. Verify that the ASCCP108a is in Draft state. (Assertion [#1](#test-assertion-1))
8. He opens the BCCP108a and clicks Draft button.
9. The developer confirms its intention in the returned message.
10. Verify that the BCCP108a is in Draft state. (Assertion [#1](#test-assertion-1))
11. He opens the ACC108a and clicks Candidate button.
12. The developer confirms its intention in the returned message.
13. Verify that the ACC108a is in Candidate state. (Assertion [#2](#test-assertion-2))
14. He opens the ASCCP108a and clicks Candidate button.
15. The developer confirms its intention in the returned message.
16. Verify that the ASCCP108a is in Candidate state. (Assertion [#2](#test-assertion-2))
17. He opens the BCCP108a and clicks Candidate button.
18. The developer confirms its intention in the returned message.
19. Verify that the BCCP108a is in Candidate state. (Assertion [#2](#test-assertion-2))
20. He opens the ACC108a and clicks Back to WIP button.
21. The developer confirms its intention in the returned message.
22. Verify that the ACC108a is in WIP state. (Assertion [#3](#test-assertion-3))
23. He opens the ASCCP108a and clicks Back to WIP button.
24. The developer confirms its intention in the returned message.
25. Verify that the ASCCP108a is in WIP state. (Assertion [#3](#test-assertion-3))
26. He opens the BCCP108a and clicks Back to WIP button.
27. The developer confirms its intention in the returned message.
28. Verify that the BCCP108a is in WIP state. (Assertion [#3](#test-assertion-3))
29. He opens the ACC108a and moves it to Draft state. Afterwards, he clicks on the Back to WIP button.
30. The developer confirms its intention in the returned message.
31. Verify that the ACC108a is in WIP state. (Assertion [#4](#test-assertion-4))
32. He opens the ASCCP108a and moves it to Draft state. Afterwards, he clicks on the Back to WIP button.
33. The developer confirms its intention in the returned message.
34. Verify that the ASCCP108a is in Draft state. (Assertion [#4](#test-assertion-4))
35. He opens the BCCP108a and moves it to Draft state. Afterwards, he clicks on the Back to WIP button.
36. The developer confirms its intention in the returned message.
37. Verify that the BCCP108a is in Draft state. (Assertion [#4](#test-assertion-4))

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

## Test Case 10.10

> Restoring developer ACC

Pre-condition: The developer is on the CC View page with the Working branch open. Deleted CCs are shown in the list.


### Test Assertion:

#### Test Assertion #1
The developer user can open an ACC and restore it. All of its associations shall be restored as well. Revision number shall be the same as before restored. Note that the ASCCs and BCCs are restored not the corresponding ASCCPs and BCCPs.

### Test Step Pre-condition:

1. There is the ASCCP11010ow owned by the developer of the test steps and it is deleted.
2. There is the BCCP11010ow owned by the developer of the test steps and it is deleted.
3. There is the ACC11010ow owned by the developer of the test steps and it is deleted. The ACC11010ow uses the ASCCP11010ow and the BCCP11010ow.

### Test Step:

1. The oagi developer logs into score.
2. He visits the CC list page, and filters CCs based on state “Deleted”.
3. He opens the ACC1 and restores it.
4. Verify that the has been active and that it is in WIP state. (Assertion [#1](#test-assertion-1))
5. The developer expands the tree of the ACC11010ow.
6. Verify that the ASCCP11010ow and the BCCP1 1010ow are active and there is no flag indicating that are deleted. (Assertion [#1](#test-assertion-1))
7. The developer goes to CC list page.
8. He clicks to open the ASCCP11010ow.
9. Verify that is active and that is in WIP state. (Assertion [#1](#test-assertion-1))
10. The developer goes to CC list page.
11. He clicks to open the BCCP11010ow.
12. Verify that is active and that is in WIP state. (Assertion [#1](#test-assertion-1))

## Test Case 10.11

> Creating a brand-new developer ASCCP

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
On the CC list page where a working branch is selected, the developer can create a brand-new ASCCP by selecting ONLY a developer ACC which is in any state and owned by any user. The ASCCP should have the following default values – Property Term = [ACC Object Class Term]; DEN = [Property Term] + “. Object Class Term” and disabled; Reusable = true; Definition = blank; Definition Source=blank; Deprecated = false and disabled; Nillable = false; Namespace = null, Comments = empty. The brand-new ASCCP must not have any release assigned yet, i.e., it must not appear in any release branch except the working branch. It has a revision number of 1. The ASCCP should have the associated ACC along with its properties but they cannot be changed. Only ACC whose Component Type is Semantics, and Semantic Group can be selected.

#### Test Assertion #2
If the underlying ACC has changed after the ASCCP was first created, the system should automatically pick up the change, e.g., when the ASCCP is opened or refreshed on the ASCCP details page.

#### Test Assertion #3
The developer cannot create a brand-new developer ASCCP when a release branch is selected.

#### Test Assertion #4
The developer cannot create a brand-new developer ASCCP when a draft release branch is selected.

#### Test Assertion #5
ACC whose component type is Extension cannot be selected for an ASCCP.

#### Test Assertion #6
Only ACC whose component type is Semantics or Semantic Group can be selected for an ASCCP.

#### Test Assertion #7
The developer can create an ASCCP from an ACC in WIP state using the function “Create ASCCP from this”. The Property Term of the created ASCCP is based on the Object Class Term of the ACC.

### Test Step Pre-condition:

1. There are the following core components:
2. The ACC1011ow that is in WIP state and owned by the developer of the test steps.
3. The ACC1011devxw that is in WIP state and owned by the developer devx.
4. The ACC1011devxd that is in Draft state and owned by the developer devx.
5. The ACC1011devxc that is in Candidate state and owned by the developer devx.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits CC page and creates a new ASCCP using the ACC1011ow.
3. Verify that in the dialog used to select an ACC, all the ACCs of the precondition are listed. (Assertion [#1](#test-assertion-1))
4. He selects the ACC1011ow .
5. Verify that the default values of the ASCCP are those mentioned in Assertion #1.
6. The developer visits the CC list page, opens the ACC1011ow and changes its Object Class Term.
7. He then opens the brand new ASCCP created in the second test step.
8. Verify that the DEN of the ASCCP has been changed according to the ACC1011ow change. (Assertion [#2](#test-assertion-2))
9. The developer visits CC List page and selects the working branch.
10. Verify that the ASCCP has a revision number 1 and it is listed. (Assertion [#1](#test-assertion-1))
11. The developer visits CC List page and selects a non-working branch.
12. Verify that the ASCCP is not listed. (Assertion [#1](#test-assertion-1))
13. Verify that the button used to create an ASCCP is not displayed. (Assertion [#3](#test-assertion-3))

## Test Case 10.12

> Editing a brand-new developer ASCCP

Pre-condition: The brand-new ASCCP is created by the developer and it is in the WIP state. The developer accesses these functionalities by opening the brand-new ASCCP from the CC list page or after creating a brand-new ASCCP according to Test Assertion #1 in Test Case 10.9.


### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the ASCCP and save the changes with the following business rules.

##### Test Assertion #1.a
The fields “Property Term”, “Reusable”, “Nillable”, “Definition”, “Definition Source”, and “Namespace” can be changed.
##### Test Assertion #1.b
Deprecated field is locked at the value false.
##### Test Assertion #1.c
The field “DEN” is automatically changed based on the changes of the “Property Term” field.
##### Test Assertion #1.d
A warning should be given when the Definition is empty.
##### Test Assertion #1.e
The fields “GUID” and “DEN” cannot be changed.
##### Test Assertion #1.f
The fields of the Associated ACC and its children nodes cannot be changed.
##### Test Assertion #1.g
The following fields are required “Property Term”, “Reusable”, “Nillable”, and “Namespace”.
##### Test Assertion #1.h
The developer can choose a new ACC for the ASCCP. ASCCP DEN shall be automatically updated.
##### Test Assertion #1.i
Only standard namespace shall be allowed for the “Namespace”.

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

##### Test Assertion #6.a
If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
##### Test Assertion #6.b
If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field

### Test Step Pre-condition:

1. There is the ASCCP11012ow that is in WIP state and owned by the developer of the test steps.
2. There is the ACC1012ow that is in WIP state, has revision number 1 and owned by the developer devx.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC list page and clicks on the ASCCP11012ow.
3. He changes the Property Term from ASCCP1012ow to ASCCP1012owchanged, he unchecks the Reusable field (makes it False), clicks on the Nillable field, sets a Definition to the Definition field and updates the ASCCP11012owchanged.
4. Verify that the ASCCP1012owchanged has been changed. (Assertion [#1.a](#test-assertion-1a))
5. Verify that the Deprecated field is false. (Assertion [#1.b](#test-assertion-1b))
6. He changes the Property Term back to ASCCP1012ow.
7. Verify that the DEN field has been changed accordingly. (Assertion [#1.c](#test-assertion-1c))
8. The developer clears the Definition field and clicks update.
9. Verify that a warning message is returned. (Assertion [#1.d](#test-assertion-1d))
10. He confirms its intension.
11. Verify that the Definition field is empty/blanck. (Assertion [#1.d](#test-assertion-1d))
12. The developer enters a definition into the Definition field and updates the ASCCPow.
13. Verify that the ASCCP1012ow has been changed. (Assertion [#1.d](#test-assertion-1d))
14. Verify that the GUID and DEN fields are disabled. (Assertion [#1.e](#test-assertion-1e))
15. The developer expands the tree of the and clicks on its associated ACC
16. Verify that the details of the associated ACC and its child nodes are disabled. (Assertion [#1.f](#test-assertion-1f))
17. The developer chooses a new ACC (e.g., the ACC1012ow) to associate it with the ASCCP1012ow.
18. Verify that the associated ACC has been changed. (Assertion [#1.g](#test-assertion-1g))
19. Verify that the DEN field has been changed according to the Object Class Term of the new associated ACC. (Assertion [#1.g](#test-assertion-1g))
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

## Test Case 10.13

> Creating a new revision of a developer ASCCP

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
On the CC Detail page of a published working branch of an ASCCP (whose revision number is the same as that of the latest release), the developer can create a new revision of the ASCCP. The result is that the working branch has that ASCCP with an incremental revision number that is in the WIP state.  Its attributes are initially the same as those of the previous revision.

### Test Step Pre-condition:

1. There is the ASCCP11013 (e.g, OAGIS10 Nouns. OAGiS10 Nouns) that is in Published Release state.

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the ASCCP11013 and creates a new revision.
3. Verify that the fields are the same as those of the previous revision. (Assertion [#1](#test-assertion-1))
4. Verify that a new revision has been created (e.g., by visiting the CC list page and verifying that the revision is greater than 1) and that the ASCCP11013 is in WIP state. (Assertion [#1](#test-assertion-1))

## Test Case 10.14

> Editing a revision of a developer ASCCP

Pre-condition: The ASCCP under test has revision number greater than 1 and is in WIP state.


### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the ASCCP and save the changes with the following business rules.

##### Test Assertion #1.a
The fields “GUID”, “Namespace”, and “Property Term” cannot be changed.
##### Test Assertion #1.b
“Definition” and “Definition Source” can be changed.
##### Test Assertion #1.c
If “Reusable” is false in the previous revision, it can be changed to true; otherwise, it cannot be changed.
##### Test Assertion #1.d
If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement ASCCP that is not already deprecated from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
##### Test Assertion #1.e
If “Nillable” is False, it can be changed to True but not vice versa.
##### Test Assertion #1.f
A warning should be given when the “Definition” is empty.
##### Test Assertion #1.g
The fields of the Associated ACC and its children nodes cannot be changed.

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
3. Verify that the fields GUID and DEN are disabled. (Assertion [#1.a](#test-assertion-1a))
4. Verify that the fields Namespace, Definition Source and Definition can be changed. (Assertion [#1.b](#test-assertion-1b))
5. He changes the Namespace to “-“ as well as he makes some valid changes to the Definition Source and Definition fields. Finally, he updates the ASCCP1014ow.
6. Verify that the Namespace, Definition Source and Definition fields have been changed accordingly. (Assertion [#1.b](#test-assertion-1b))
7. The developer opens the ASCCP1014ow.
8. Verify that the Reusable field is False and enabled. (Assertion [#1.c](#test-assertion-1c))
9. He changes it to True and clicks the Update button.
10. Verify that the field has been changed. (Assertion [#1.c](#test-assertion-1c))
11. The developer goes to CC list page and clicks to view ASCCP11014ow.
12. Verify that the Reusable field is True and disabled.
13. The developer goes back to CC list page and he opens the ASCCP11014ow.
14. …
15. Verify that the Nillable field can be changed. (Assertion [#1.e](#test-assertion-1e))
16. He changes Nillable to True and clicks the Update button.
17. Verify that the ASCCP11014ow has been changed. (Assertion [#1.e](#test-assertion-1e))
18. The developer visits the CC list page and opens to view ASCCP11014ow
19. Verify that the Nillable field is True and disabled. (Assertion [#1.e](#test-assertion-1e))
20. The developer opens the ASCCP11014ow.
21. He clears the Definition field and clicks the Update button.
22. Verify that a warning message is returned asking him to confirm its intention. (Assertion [#1.f](#test-assertion-1f))
23. He confirms its intension.
24. Verify that the Definition field is empty/blank. (Assertion [#1.f](#test-assertion-1f))
25. The developer expands the ASCCP11014ow tree.
26. Verify that the details of its associated ACC cannot be changed. (Assertion [#1.g](#test-assertion-1g))
27. Verify that the details of the nodes of its associated ACC cannot be changed. (Assertion [#1.g](#test-assertion-1g))
28. The developer tries to change the associated ACC of the ASCCP11014ow.
29. Verify that there is no button used for changing the associated ACC. (Assertion [#2](#test-assertion-2))
30. …

## Test Case 10.15

> Developer ASCCP state management

Pre-condition: The user is on the ASCCP detail page, which he owns.
All these state changes need a confirmation dialog box with slightly different messages. Changing to the Draft state only need a confirmation. Retracting a Candidate ASCCP to WIP needs a confirmation.


### Test Assertion:

#### Test Assertion #1
The developer can change the ASCCP state from WIP to Draft.

#### Test Assertion #2
The developer can change the ASCCP state from Draft back to WIP.

#### Test Assertion #3
The developer can change the ASCCP state from Draft to Candidate.

#### Test Assertion #4
The developer can retract an ASCCP which is in Candidate state back to the WIP state.

### Test Step Pre-condition:

1. There are the following CCs:
2. ACC11015ow that is owned by the developer conducting the test steps and is in WIP state.
3. ASCCP11015ow that is owned by the developer conducting the test steps, is in WIP state and uses the ACC11015ow.
4. ASCCP21015ow that is owned by the developer conducting the test steps and is in WIP state.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC list page and clicks to view ASCCP21015ow.
3. He moves the ASCCP21015ow to the Draft state and he confirms his intension to a returned message.
4. Verify that the is in Draft state. (Assertion [#1](#test-assertion-1))
5. The developer visits the CC list page and clicks to view ASCCP11015ow.
6. He moves the ASCCP11015ow to the Draft state and he confirms his intension to a returned message.
7. Verify that a message asking him if he wishes to move the ACC11015ow to the Draft state as well. (Assertion [#1](#test-assertion-1))
8. He provides his permission for this.
9. Verify that the ACC11015ow is in Draft state. (Assertion [#1](#test-assertion-1))
10. The developer visits the CC list page and clicks to view ASCCP21015ow.
11. He moves the ASCCP21015ow back to WIP state while he confirms his intension to a message returned.
12. Verify that the is ASCCP21015ow in WIP state. (Assertion [#2](#test-assertion-2))
13. The developer moves the ASCCP21015ow to the Draft state and then to the Candidate while he confirms his intension to do so to a returned message.
14. Verify that the ASCCP21015ow is in Candidate state. (Assertion [#3](#test-assertion-3))
15. The developer visits the CC list page and clicks to view ASCCP11015ow.
16. He moves it to the Candidate state and confirms its intension to a returned message.
17. Verify that a message asking him if he wishes to move the ACC11015ow to the Candidate state as well. (Assertion [#3](#test-assertion-3))
18. He provides his permission for this.
19. Verify that the ACC11015ow is in Candidate state. (Assertion [#3](#test-assertion-3))
20. The developer visits the CC list page and opens the ASCCP21015ow.
21. He moves it back to WIP state (i.e., he retracts it) and he confirms its intention to a returned message.
22. Verify that the ASCCP21015ow is in WIP state. (Assertion [#4](#test-assertion-4))

## Test Case 10.16

> Deleting a developer ASCCP

Pre-condition: N/A
Delete a CC means that it is marked as “Deleted” and it is still displayed in the CC list when the working branch is selected. If a CC is “Deleted” any other developer can restore it.


### Test Assertion:

#### Test Assertion #1
If an ASCCP revision number is 1, the developer owner can delete it when it is in WIP state. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the CC list page.

#### Test Assertion #2
Upon opening an ancestor ACC that has an ACC using a deleted ASCCP, the ancestor ACC shall be flagged that it is in an invalid state. And as the ancestor ACC is expanded down to the ACC that contains the deleted ASCCP, the system shall be able to flag that the ASCCP has been deleted.

#### Test Assertion #3
Upon opening an ACC that has an ASCC using a deleted ASCCP, the system shall be able to flag that the ACC is in an invalid state and that the ASCCP is in the deleted state. The system shall provide an option for the developer to choose another ASCCP for the ASCC. The system shall also allow the developer to open the deleted ASCCP in another tab where he can restore it. Then system shall be able to clear the flags afterward (e.g., when the developer refreshes the ACC).

#### Test Assertion #4
ASCCP whose revision number is more than 1 and is in any state cannot be deleted.

### Test Step Pre-condition:

1. There is the ASCCP11016ow owned by the developer of the test steps that is in WIP state and its revision number is 1.
2. There is the ASCCP11016od owned by the developer of the test steps that is in Draft state and its revision number is 1.
3. There is the ASCCP11016oc owned by the developer of the test steps that is in Candidate state and its revision number is 1.
4. There is the ACC11016ow owned by the developer of the test steps that is in WIP state and uses the ASCCP11016ow.
5. There is the ASCCP2 (e.g., Acknowledge Credit Transfer. Acknowledge Credit Transfer) that is in WIP state and has a revision number 2.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC list page and he opens the ASCCP11016ow.
3. He clicks delete button.
4. Verify that a confirmation message is returned asking for his approval. (Assertion [#1](#test-assertion-1))
5. He verifies his intension.
6. Verify that the CC list page is returned and that the ASCCP11016ow is in Deleted state. (Assertion [#1](#test-assertion-1))
7. He opens the ASCCP11016od and tries to delete it.
8. Verify that there is no Delete button. (Assertion [#1](#test-assertion-1))
9. He opens the ASCCP11016oc and tries to delete it.
10. Verify that there is no Delete button. (Assertion [#1](#test-assertion-1))
11. The developer opens the ACC11016ow and expands its tree.
12. Verify that there is an indicator showing that the ASCCP11016ow is deleted. (Assertion [#2](#test-assertion-2))
13. The developer can change the ASCCP or the ASCC…..<- not yet implemented
14. …TA3??
15. The developer clicks on the flag which indicates that the ASCCP11016ow is deleted.
16. Verify that a new tab is created. (Assertion [#3](#test-assertion-3))
17. The developer restores the ASCCP11016ow.
18. He closes the new tab and goes to the first tab.
19. The developer refreshes the page (or he opens the ACC11016ow again)
20. Verify that there is no flag indicating that the is deleted. (Assertion [#3](#test-assertion-3))
21. The developer opens the ASCCP21016ow and tries to delete it.
22. Verify that there is no delete button. (Assertion [#4](#test-assertion-4))
23. The developer moves the ASCCP21016ow to the draft state and tries to delete it.
24. Verify that there is no delete button. (Assertion [#4](#test-assertion-4))
25. The developer moves the ASCCP21016ow to the candidate state and tries to delete it.
26. Verify that there is no delete button. (Assertion [#4](#test-assertion-4))

## Test Case 10.17

> Restoring a developer ASCCP

Pre-condition: The developer is on the CC View page with the working branch open. Some Deleted CCs are shown in the list may be with “Deleted” state is selected in the state filter box. The developer opens the ASCCP to see its detail.


### Test Assertion:

#### Test Assertion #1
The developer user can restore a deleted ASCCP whose ACC is still alive.

#### Test Assertion #2
The developer user can restore a deleted ASCCP whose ACC is deleted. The UI shall display a flag in the ASCCP detail page that the ASCCP is in an invalid state and that its ACC is in the deleted state.

### Test Step Pre-condition:

1. There is the ASCCP11017odel owned by the developer of the test steps and it is deleted.
2. There is the ASCCP21017devxdel owned by the developer devx and it is deleted.
3. There is the ACC31017odel owned by the developer of the test steps and it is deleted.
4. There is the ASCCP31017odel owned by the developer of the test steps, is in deleted state and uses the ACC11017odel which is deleted and owned by the same developer.

### Test Step:

1. The oagi developer logs into score.
2. He visits the CC list page, and filters CCs based on state “Deleted”.
3. He opens the ASCCP11017odel and restores it.
4. Verify that the has been active and that it is in WIP state. (Assertion [#1](#test-assertion-1))
5. The developer visits the CC list page and opens the ASCCP21017devxdel.
6. He tries to restore it.
7. Verify that there is no Restore button or it is disabled. (Assertion [#1](#test-assertion-1))
8. The developer visits the CC list page and opens the ASCCP31017odel.
9. He restores the ASCCP31017odel.
10. He expands the tree of the ASCCP31017odel.
11. Verify that there is a flag indicating that the ACC11017odel is deleted. (Assertion [#2](#test-assertion-2))

## Test Case 10.18

> Creating a brand-new developer BCCP

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
On the CC list page where a working branch is selected, the developer can create a brand-new BCCP by selecting a BDT which can be in any state and belongs to any developer. The BDT choice shall be, by default, is empty. Filtering field is used to filter the commonly-used BDT (BDTs may also be classified as Default, Qualified, and Unqualified - see section 4.1.1.12.1 in the SRT Design Document version 2.4 to understand what is unqualified BDT ), but the user has a choice to be able to select any BDT (type > 1). The BCCP should have the following default values – Property Term = “Property Term”; DEN = “Property Term. “ + BDT_Data_Type_Term and disable; Nillable = false; Deprecated = false and disabled; Value Constraint= None (Default and Fixed value should be empty); Definition = blank; Definition Source = blank; Namespace = null, Comments = empty. The brand-new BCCP must not have any specific release assigned yet, i.e., it must not appear in any release branch except the working branch. It has a revision number 1. The BCCP should have the associated BDT details but cannot be changed. BDT supplementary components are displayed in the tree but their details cannot be changed.

#### Test Assertion #2
The developer cannot create a brand-new BCCP when a release branch is selected.

### Test Step Pre-condition:



### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC page and click the “Create BCCP” button.
3. He chooses a BDT to create a BCCP.
4. Verify that all the fields and their defaults values exist. Also, verify that he cannot change the values of the BDT fields. (Assertion [#1](#test-assertion-1))
5. He visits the CC page again.
6. He selects a release branch (e.g., 10.6)
7. Verify that there is no “Create BCCP” button. (Assertion [#2](#test-assertion-2))

## Test Case 10.19

> Editing a brand-new developer BCCP

Pre-condition: The brand-new BCCP is created by the developer and it is in the WIP state. The developer accesses these functionalities by opening the brand-new BCCP from the CC list page or after creating a brand-new BCCP according to Test Assertion #1 of the Test Case 10.18.


### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the BCCP and save the changes with the following business rules.

##### Test Assertion #1.a
The fields “GUID”, “DEN” and “Deprecated” cannot be changed.
##### Test Assertion #1.b
The fields “Property Term”, “Nillable”, “Value Constraint (Default or Fixed Value)”, “Namespace”, “Definition Source” and “Definition” can be changed. “Property Term”, “Nillable”, and “Namespace” are required.
##### Test Assertion #1.c
The field “DEN” is automatically changed based on the changes of the “Property Term” field.
##### Test Assertion #1.d
The fields “Default Value” and “Fixed Value” are mutually exclusive.
##### Test Assertion #1.e
The fields “Fixed Value” and “Nillable” are mutually exclusive.
##### Test Assertion #1.f
A warning should be given when the Definition is empty.
##### Test Assertion #1.g
The fields of the BDT and its components cannot be changed.
##### Test Assertion #1.h
Only standard namespace shall be allowed for the “Namespace”.

#### Test Assertion #2
The developer can change the BDT to another one.

#### Test Assertion #3
The developer can transfer ownership of the BCCP to another developer while in the WIP state but not end user.

#### Test Assertion #4
When the BCCP DEN changes, all BCCs which uses the BCCP and whose revision numbers are 1 shall have their DEN updated accordingly.

#### Test Assertion #5
The end user can Exclude SCs or not from the Searching Field by checking or unchecking the “Exclude SCs” checkbox accordingly.

##### Test Assertion #5.a
If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
##### Test Assertion #5.b
If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field

### Test Step Pre-condition:

1. There is a BCCP, say BCCP1, which is a brand new BCCP and it is in WIP state and owned by the developer conducting the test steps.

### Test Step:

1. An OAGi developer logs into the system.
2. The developer opens BCCP11019ow.
3. Verify that the GUID, DEN and Deprecated fields cannot be changed (they are disabled). (Assertion [#1.a](#test-assertion-1a))
4. He changes all the fields expect “Nillable” checkbox (he leaves it unchecked). He also set Fixed value and updates the BCCP11019ow.
5. Verify that the BCCP11019ow been successfully updated. Also verify that the “DEN” field has updated based on new “Property Term”. (Assertion [#1.b](#test-assertion-1b), 1.3)
6. He sets the Default value and updates the BCCP11019ow.
7. Verify that he cannot set the “Fixed value” (there is no such field if he selects the “Default value” field of the selector list) and that the BCCP11019ow has been successfully updated. (Assertion [#1.d](#test-assertion-1d))
8. He checks the “Nillable” field.
9. Verify that he cannot select the “Fixed Value” field (he cannot click on that field of the selector list). (Assertion [#1.e](#test-assertion-1e))
10. He leaves the “Definition” field blank.
11. Verify that a warning message is returned saying that the “Definition” field has been left blank. (Assertion [#1.f](#test-assertion-1f))
12. Verify that he cannot change the fields of the BDT. (all of them are disabled) (Assertion [#1.g](#test-assertion-1g))
13. He changes the BDT of the BCCP11019ow (e.g., he uses the BDT “Telephone Value. Type”)
14. Verify that the BDT has been changed (e.g., by checking that the “Number Format. Value” exists) (Assertion [#2](#test-assertion-2))
15. ..
16. The developer visits the CC list page and click on the Transfer ownership button of the BCCP11019ow.
17. Verify the in the dialog box there is no end user account displayed. (Assertion [#4](#test-assertion-4))
18. He chooses the developer devx to transfer the ownership of the BCCP11019ow.
19. Verify that the belongs to the developer devx (e.g., by checking the owner field in the CC list page). (Assertion [#4](#test-assertion-4))
20. …

## Test Case 10.20

> Creating a new revision of a developer BCCP

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
On the CC Detail page of a published BCCP in working branch, the developer can create a new revision of the BCCP. The result is that the Working branch has that BCCP with an incremental revision number that is in the WIP state.  Its attributes are initially the same as those of the previous revision.

### Test Step Pre-condition:

1. There is the BCCP2 that is in Published Release state.

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the BCCP2 and creates a new revision.
3. Verify that the fields are the same as those of the previous revision. (Assertion [#1](#test-assertion-1))
4. Verify that a new revision has been created. (e.g, by visiting the CC list page and verifying that the revision is greater than 1) (Assertion [#1](#test-assertion-1))

## Test Case 10.21

> Editing a revision of a developer BCCP

Pre-condition: The BCCP under test has revision number greater than 1 and is in WIP state.


### Test Assertion:

#### Test Assertion #1
The developer can change the details of the BCCP and save the changes with the following business rules.

##### Test Assertion #1.a
The fields “GUID”, “DEN”, “Namespace”, and “Property Term” cannot be changed.
##### Test Assertion #1.b
If a fixed value is already applied, it cannot be changed (hence neither default nor nillable can change).
##### Test Assertion #1.c
If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement BCCP that is not already deprecated from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
##### Test Assertion #1.d
If nillable can change (no fixed value and nillable is false), it can only be changed from false to true.
##### Test Assertion #1.e
If the default value can change (no fixed value), it can change to any valid value w.r.t. the primitive.
##### Test Assertion #1.f
Definition and Definition Source can change.
##### Test Assertion #1.g
A warning should be given when the Definition is empty.
##### Test Assertion #1.h
The fields of the BDT and its supplementary components cannot be changed.

#### Test Assertion #2
The associated BDT can be changed.

#### Test Assertion #3
The developer can cancel the revision. In this case, the system rollbacks the BCCP changes during the revision. History of those changes are in the history record. There must be a confirmation dialog box.

### Test Step Pre-condition:

1. There is a BCCP (e.g., Effectivity Relation Code. Code), say BCCP31021ow, which is in WIP state and has a revision number greater than 1 and owned by the developer conducting the test steps.

### Test Step:

1. An OAGi developer logs into the system.
2. The developer opens BCCP31021ow and changes the Definition Field.
3. Verify that the GUID, DEN and Property Term fields cannot be changed (they are disabled) and that the Definition field has been updated. (Assertion [#1.a](#test-assertion-1a) 1.6)
4. He opens the BCCP “Ownership Type Code” that has Nillable=False, he creates a new revision of it and he sets it to True.
5. Verify that the change has been successfully recorded. (Assertion # 1.4)
6. He opens the BCCP “Adjusted Invoice Total Amount” that has Nillable=True and he creates a new revision of it.
7. Verify that he cannot change it to False. (Assertion # 1.4)
8. The developer opens BCCP31021ow, changes the Default Value and Definition Source field, leaves the Definition field empty and updates it.
9. Verify that a Warning message is returned. Also, verify that the BCCP3 has been changed successfully. (Assertion [#1.f](#test-assertion-1f) 1.7)
10. Verify that the BDT fields cannot be changed. (Assertion # 1.8)
11. He changes the BDT of the BCCP31021ow
12. Verify that the BDT has been changed (e.g., by checking that the “Number Format. Value” exists) (Assertion [#2](#test-assertion-2))
13. …

## Test Case 10.22

> Developer BCCP state management

Pre-condition: The user is on the BCCP detail page, which he owns.
All these state changes need a confirmation dialog box with slightly different messages.


### Test Assertion:

#### Test Assertion #1
The developer can change the BCCP state from WIP to Draft.

#### Test Assertion #2
The developer can change the BCCP state from Draft back to WIP.

#### Test Assertion #3
The developer can change the BCCP state from Draft to Candidate.

#### Test Assertion #4
The developer can change the BCCP state from Candidate back to WIP.

### Test Step Pre-condition:

1. There is a BCCP, say BCCP4, which is in WIP state with revision number 1.
2. The working branch is selected

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the BCCP4 and sets it to Draft state while he confirms his intention.
3. Verify that the BCCP4 is in Draft state. (Assertion [#1](#test-assertion-1))
4. He sets BCCP4 back to WIP again while he confirms his intention.
5. Verify that the BCCP4 is in WIP state. (Assertion [#2](#test-assertion-2))
6. He sets the BCCP4 to Draft and then to Candidate state while he confirms his intention.
7. Verify that the BCCP4 is in Candidate state. (Assertion [#3](#test-assertion-3))
8. He opens the BCCP4 and sets it back to WIP state while he confirms his intention..
9. Verify that the BCCP4 is in WIP state. (Assertion [#4](#test-assertion-4))

## Test Case 10.23

> Deleting developer BCCP

Pre-condition: N/A
Delete a CC means that it is marked as “Deleted” and it is still displayed in the CC list when the working branch is selected. Its detail can also be viewed. If a CC is “Deleted” any other developer can restore it as described in the following Test Case 10.24.


### Test Assertion:

#### Test Assertion #1
If a BCCP revision number is 1, the developer owner can delete it when it is in WIP state. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the CC list page.

#### Test Assertion #2
Upon opening an ancestor ACC that has an ACC using a deleted BCCP, the ACC should be flagged as it is in an invalid state and as the ancestor ACC is expanded down to the ACC that contains the deleted BCCP, the system shall be able to flag that the BCCP is in the deleted state. Test this for when there is a descendant ACC that is a group as well.

#### Test Assertion #3
Upon opening an ACC that has a BCC using a deleted BCCP, the ACC shall be flagged as in an invalid state and the BCCP shall be flagged as in the deleted state. The system shall provide an option for the developer to choose another BCCP for the BCC. The system shall also allow the developer to open the deleted BCCP in another tab or dialog where he can restore it, even if the BCCP is owned by another developer. Then, the system shall be able to clear the flag, e.g., when the developer refreshes the ACC.

#### Test Assertion #4
BCCP whose revision number is more than 1 in any state cannot be deleted.

### Test Step Pre-condition:

1. There is the BCCP11023ow owned by the developer of the test steps that is in WIP state and its revision number is 1.
2. There is the BCCP11023od owned by the developer of the test steps that is in Draft state and its revision number is 1.
3. There is the BCCP11023oc owned by the developer of the test steps that is in Candidate state and its revision number is 1.
4. There is the ACC11023ow owned by the developer of the test steps that is in WIP state and uses the BCCP11023ow.
5. There is the BCCP21023ow (e.g., Record Set Reference Id. Identifier) that is in WIP state and has a revision number 2.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC list page and he opens the BCCP11023ow.
3. He clicks delete button.
4. Verify that a confirmation message is returned asking for his approval. (Assertion [#1](#test-assertion-1))
5. He verifies his intension.
6. Verify that the CC list page is returned and that the BCCP11023ow is in Deleted state. (Assertion [#1](#test-assertion-1))
7. He opens the BCCP11023od and tries to delete it.
8. Verify that there is no Delete button. (Assertion [#1](#test-assertion-1))
9. He opens the BCCP11023oc and tries to delete it.
10. Verify that there is no Delete button. (Assertion [#1](#test-assertion-1))
11. The developer opens the ACC11023ow and expands its tree.
12. Verify that there is an indicator showing that the BCCP11023ow is deleted. (Assertion [#2](#test-assertion-2))
13. The developer clicks on the indicator.
14. Verify that a new tab is returned where the developer can view the BCCP11023ow.
15. He restores the BCCP11023ow and closes the new tab.
16. He refreshes the page where he viewed the ACC11023ow.
17. Verify that there is no indicator about that the BCCP11023ow is deleted. (Assertion [#3](#test-assertion-3))
18. The developer opens the BCCP21023ow and tries to delete it.
19. Verify that there is no delete button. (Assertion [#4](#test-assertion-4))
20. The developer moves the BCCP21023ow to the draft state and tries to delete it.
21. Verify that there is no delete button. (Assertion [#4](#test-assertion-4))
22. The developer moves the BCCP21023ow to the candidate state and tries to delete it.
23. Verify that there is no delete button. (Assertion [#4](#test-assertion-4))

## Test Case 10.24

> Restoring developer BCCP

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
The developer user can restore a deleted BCCP whose BDT is still alive.

#### Test Assertion #2
The developer user can restore a deleted BCCP whose BDT is deleted. The UI display a flag in the BCCP detail page that its BDT is in deleted state.

### Test Step Pre-condition:

1. There is the BCCP11024odel owned by the developer of the test steps and it is deleted.
2. There is the BCCP21024devxdel owned by the developer devx and it is deleted.

### Test Step:

1. The oagi developer logs into score.
2. He visits the CC list page, and filters CCs based on state “Deleted”.
3. He opens the BCCP11024odel and restores it.
4. Verify that the has been active and that it is in WIP state. (Assertion [#1](#test-assertion-1))
5. The developer visits the CC list page and opens the BCCP21024devxdel.
6. He tries to restore it.
7. Verify that there is no Restore button or it is disabled. (Assertion [#1](#test-assertion-1))