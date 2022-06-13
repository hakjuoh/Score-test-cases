## Test Case 10.4

> Editing associations of a brand-new developer ACC

Pre-condition: The brand-new ACC is created by the developer and is in the WIP state. The developer accesses these functionalities by opening the brand-new ACC from the CC list page or after creating a brand-new ACC according to Test Assertion #1 of the Test Case 10.2.

### Test Assertion:

#### Test Assertion #1
The developer can append a developer ASCCP to the ACC (maybe by right-clicking the ACC) that results in an association to a developer ASCCP. The default value of the new ASCC shall be as follows: Min = 0, Max = “unbounded”, Deprecated = false and disabled, Definition=empty, Definition Source=empty.

	1. The developer ASCCP can be in any state.
	2. A warning shall be given if the ASCCP is deprecated.
	3. The ACC shall not already contain an ASCCP or BCCP with the same property term whether in itself or within its based ACC. (maybe, the ASCCP with the same property should not appear in the list of the dialog used to append ASCCPs. Note that there may be multiple ASCCPs with the same property term even in the same release – this situation occurs with the Data Area ASCCP. But maybe easier to test if giving error after a problematic ASCCP is selected). The test should account for the cases of group ASCCP – 1) there is a group in the based ACC, the developer appends a non-group ASSCP that has the same property term as a property in the group of the based ACC; 2) there is a group in the based ACC, the developer appends a group ASCCP that has a child with the same property term as a property in the group of the based ACC; 3) The ACC has a group ASCCP and the developer appends an ASCCP that has the same property term as a property in the group; 4) The ACC has a group ASCCP and the developer appends another group ASCCP that cause the two groups to have some duplicate property terms; 5) same as (1) to (4) but groups have a cascaded a group.
	4. The resulting ASCC shall be in the WIP state.
	5. If the ASCCP is not reusable, check that there is no ASCC already using it. Also test for when non-reusable ASCCP has been deleted while still having an association and the developer still try to user the ASCCP in another association.
	6. No end user ASCCP can be selected.

#### Test Assertion #2
The developer can right-click on any associations and Insert an ASCCP before or after. The rest of the behavior is the same as test assertion #1.

#### Test Assertion #3
The developer can update the following fields of its new ASCC (rev = 1); Min, Max, Definition, Definition Source. I.e., he cannot update the details of the ASCCP. The following business rules are applied:

	1. Min >= 0
	2. Max >= -1 and (Max >= Min when Max != -1)
	3. The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
	4. Min, Max, and Deprecated are required.
	5. A warning should be given when the Definition is empty.
	6. Deprecated must be false and locked (because it is a new association, it shouldn’t be deprecated).

#### Test Assertion #4
The developer can append a developer BCCP to an ACC (maybe by right clicking the ACC) that results in an association to the developer BCCP. The default value of the new BCC shall be as follows: Min=0, Max = “unbounded”, Deprecated = false and disabled, Entity Type = Element, Value Constraint= None (Default and Fixed value should be empty), Definition = empty, Definition Source = empty.

	1. The developer BCCP can be in any state.
	2. A warning shall be given if the BCCP is deprecated.
	3. The ACC shall not already contain a BCCP or ASCCP with the same property term whether in itself or within its based ACC. See TA 1.3 for different testing situations to cover.
	4. The resulting BCC shall be in the WIP state.

#### Test Assertion #5
No end user BCCP can be selected.The developer can right-click on any associations and choose insert a BCCP before or after it. The rest of the behavior is the same as test assertion #4.

#### Test Assertion #6
The developer can edit the following info of a BCC - Min, Max, Entity Type, Default or Fixed Value, Definition, and Definition Source. He cannot update the BCCP information. The following business rules apply:

	1. Min >= 0
	2. Max >= -1 and (Max >= Min when Max != -1)
	3. The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
	4. All fields except Definition and Definition Source are required. However, a warning should be given when the Definition is empty.
	5. Deprecated must be false (because it is a new association, it shouldn’t be deprecated).
	6. The Default and Fixed value shall be disabled and cleared of value if the Entity Type is Element. The system shall warn the user that the Default and Fixed Value will be cleared if changing entity type to Element. If enabled, the Default and Fixed value shall be mutually exclusive.
	7. The Attribute Entity Type can be applied only if the BCCP has no SC or all SCs have max cardinality zero.
	8. If the Entity Type is changed from Element to Attribute the Min Cardinality should be changed to 0 and the Max Cardinality to 1.

#### Test Assertion #7
The developer can change (move up or down) the sequence of an association to an ASCCP. It would be good to be able to drag-n-drop instead of moving up or down.

#### Test Assertion #8
The developer can change (move up or down) the sequence of an association to a BCCP. It would be good to be able to drag-n-drop instead of moving up or down.

#### Test Assertion #9
The developer can remove an association (ASCC or BCC), there must be a confirmation dialog box though. (In that case, the association information is stored in the history record).

#### Test Assertion #10
The developer can assign another developer ACC belonging to the working branch as a base of this ACC.

	1. The base ACC can be in any state.
	2. If the chosen base ACC is deprecated, a warning shall be given.
	3. The base ACC shall only be Base or Semantics component type (not be a Group, User Extension Group, or Embedded component type, etc.).
	4. The developer cannot change the fields of the base ACC.
	5. End user ACC cannot be selected as a base.
	6. Duplicate property term needs to be checked. See TA 1.3 for different testing situations to cover. In addition, the case of multiple layers of inheritance needs to be taken into account.

#### Test Assertion #11
The developer can remove the based ACC when one exists.

#### Test Assertion #12
The developer can transfer the ownership of an ACC, ONLY when it is in WIP states and owned by him, to ONLY another developer. In that case the ownership of the associations (ASCC and BCC) are transferred as well.

#### Test Assertion #13
The developer can refactor an ASCCP to base ACC providing that the base ACC is in WIP state, owned by the developer and there is no association to the refactoring ASCCP within base ACC hierarchy neither there is an association to the refactoring ASCCP within the ACCs that have the base ACC within their hierarchy.

#### Test Assertion #14
The developer cannot refactor an ASCCP to base ACC if

	1. The base ACC is in Draft state
	2. The base ACC is in Candidate state
	3. The base ACC is in Published state
	4. The base ACC in Deleted
	5. The base ACC is owned by another developer regardless of the state

#### Test Assertion #15
The developer cannot refactor an ASCCP to base ACC if the latter already contains this ASCCP either directly on indirectly in its hierarchy. When the developer selects the base ACC, he should be able to validate the choice. This means that Score should display all ACCs that the developer should take some action. After the developer takes that actions, Score deletes the associations to the ASCCPs that are same as the refactoring ASCCP (duplicate ASCCPs) and moves the refactoring ASCCP to the selected base ACC. Check for:

	1. Moving an ACC to WIP state
	2. Take the ownership of an ACC and move it to WIP state
	3. which are not in WIP state and those not in WIP state that also contain the refactoring

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

	1. The base ACC is in Draft state
	2. The base ACC is in Candidate state
	3. The base ACC is in Published state
	4. The base ACC in Deleted
	5. The base ACC is owned by another developer regardless of the state

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