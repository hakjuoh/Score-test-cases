## Test Case 10.7

> Editing associations of a revision of a developer ACC

Pre-condition: The ACC revision (> 1) is created by the developer and is in the WIP state. The developer accesses these functionalities by opening an ACC revision (> 1) from the CC list page or after creating a ACC revision according to Test Assertion #1 of the Test Case 10.5.
Note: Association revision number of a new association changes to the same as ACC revision number when the ACC enters the published state.


### Test Assertion:

#### Test Assertion #1
The developer can append a developer ASCCP to an ACC that results in an association to the developer ASCCP. The default value of the new ASCC shall be as follows: Min = 0, Max = “unbounded”, Deprecated = false and disabled, Definition=empty, Definition Source = empty.

	1. The developer ASCCP can be in any state.
	2. A warning shall be given if the ASCCP is deprecated.
	3. The ACC shall not already contain an ASCCP or BCCP with the same property term whether in itself or within its based ACC. The ASCCP should not appear in the list of the dialog used to append ASCCPs or return an error after selection of violating BCCP or ASCCP. See TA 1.3 in Test Case 10.4 for different testing situations to cover.
	4. The resulting ASCC shall be in the WIP state.
	5. If the ASCCP is not reusable, check that there is no ASCC already using it. If there is an ASCC already using the ASCCP, the system shall report that the ASCCP is not reusable and that it is already used.
	6. End user ASCCPs cannot be appended

#### Test Assertion #2
On a particular association, the developer can insert an ASCCP before or after it. The rest of the behavior is the same as test assertion #1.

#### Test Assertion #3
The developer can update the following fields of its new ASCC (rev = 1); Min, Max, Definition, Definition Source. I.e., he cannot update the details of the ASCCP. The following business rules are applied:

	1. Min >= 0
	2. Max >= -1 and (Max >= Min when Max != -1)
	3. The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
	4. Min, Max, and Deprecated are required.
	5. A warning should be given when the Definition is empty.
	6. Deprecated must be false and locked (because it is a new association, it shouldn’t be deprecated).

#### Test Assertion #4
The developer can edit the information of existing ASCC (ASCC whose revision > 1) following these rules.

	1. 0 <= Min <= PreviousMin
	2. If Previous-Max = -1, it cannot be changed; otherwise, Max = -1 or Max >= Previous-Max
	3. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement ASCC or BCC (filtered out the deprecated ones) within the ACC from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	4. A warning should be given when the Definition is empty.

#### Test Assertion #5
The developer can append a developer BCCP to an ACC that results in an association to the developer BCCP. The default value of the new BCC shall be as follows: Min=0, Max = “unbounded”, Deprecated = false and disabled, Entity Type = Element, Value Constraint= None (Default and Fixed value should be empty), Definition = empty, Definition Source = empty.

	1. The developer BCCP can be in any state.
	2. A warning shall be given if the BCCP is deprecated.
	3. The ACC shall not already contain an ASCCP or BCCP with the same property term whether in itself or within its based ACC. See TA 1.3 in Test Case 10.4 for different testing situations to cover.
	4. The resulting BCC shall be in the WIP state.
	5. End user BCCP cannot be appended.

#### Test Assertion #6
On a particular association and the developer can insert a BCCP before after it”. The rest of the behavior is the same as test assertion #5.

#### Test Assertion #7
The developer can edit the following info of the new BCC - Min, Max, Entity Type, Default or Fixed Value, Definition, and Definition Source. He cannot update the BCCP information. The following business rules apply:

	1. Min >= 0
	2. Max >= -1 and (Max >= Min when Max != -1)
	3. The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
	4. All fields except Definition and Definition Source are required. However, a warning should be given when the Definition is empty.
	5. Deprecated must be false (because it is a new association, it shouldn’t be deprecated).
	6. The Default and Fixed value shall be disabled and cleared of value if the Entity Type is Element. The system shall warn the user that the Default and Fixed Value will be cleared if changing entity type to Element. If enabled, the Default and Fixed value shall be mutually exclusive.
	7. If the Entity Type is changed from Element to Attribute the Min Cardinality should be changed to 0 and the Max Cardinality to 1.

#### Test Assertion #8
The developer can edit the following information of existing BCC (BCC whose revision >1).

	1. 0 <= Min <= PreviousMin
	2. If Previous-Max = -1, it cannot be changed; otherwise, Max = -1 or Max >= Previous-Max
	3. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If it was False in the previous revision the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement ASCC or BCC (filtered out the deprecated ones) within the ACC from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	4. A warning should be given when the Definition is empty.
	5. Entity Type cannot be changed.
	6. If Entity Type is Attribute, Default and Fixed Value can be changed but mutually exclusive. If Entity Type is Element, Default and Fixed Value must be disabled. The Attribute Entity Type can be applied only if the BCCP has no SC or all SCs have max cardinality zero.

#### Test Assertion #9
The developer can change (move up or down) the sequence of the brand-new and existing association to an ASCCP. It would be good to be able to drag-n-drop instead of moving up or down. Existing associations cannot be moved.

#### Test Assertion #10
The developer can change (move up or down) the sequence of the brand-new and existing association to a BCCP. It would be good to be able to drag-n-drop instead of moving up or down. Existing associations cannot be moved.

#### Test Assertion #11
The developer can remove an existing new association (ASCC or BCC) added in this revision (new association added during this revision should still have revision #1), there must be a confirmation dialog box though. However, an association cannot be removed if it is used as a replacement of a deprecated association. Information about the removed association is kept in the history record. The developer can also remove an association added to a previous revision. There should also be a confirmation dialog. If the developer cancel the revision, the removed associations should be restored.

#### Test Assertion #12
The developer can assign another developer ACC belonging to the working branch as a base of this ACC, both in the case where a based ACC does and does not already exist in the previous revision.

	1. The base ACC can be in any state.
	2. If the chosen base ACC is deprecated, a warning shall be given.
	3. The base ACC shall not be a Group, User Extension Group, or Embedded component type.
	4. The developer cannot change the fields of the base ACC.
	5. The base ACC should not contain an ASCCP or a BCCP with the same property term as that already in the ACC itself (property uniqueness).
	6. Duplicate property term needs to be checked. See TA 1.3 for different testing situations to cover. In addition, multiple layers of inheritance need to be taken into account.

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