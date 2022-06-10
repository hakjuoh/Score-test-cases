## Test Case 15.8

> Editing associations of a brand-new end user ACC

Pre-condition: The revision number of ACC under test is 1 and it is in WIP state.



### Test Assertion:

1. The end user can append an ASCCP to an ACC that results in an association to the (developer or end user) ASCCP in the same release in any state. The default value of the new ASCC shall be as follows: Min = 0, Max = “unbounded”, Deprecated = false and disabled, Definition=empty, Definition Source=empty.
	1. The selected ASCCP can be in any state.
	2. A warning shall be given if the ASCCP is deprecated.
	3. The ACC shall not already contain an ASCCP or BCCP with the same property term whether in itself or within its based ACC. (maybe the ASCCP with the same property term should not appear in the list of the dialog used to append ASCCPs. Note that there may be multiple ASCCPs with the same property term even in the same release – this situation occurs with the Data Area ASCCP).
	4. The resulting ASCC shall be in the WIP state.
	5. If the ASCCP is not reusable, check that there is no ASCC already using it.
2. The end user can click on any associations and insert an ASCCP before or after it. The rest of the behavior is the same as test assertion #1.
3. The end user can update the following fields of its new ASCC (rev = 1); Min, Max, Definition, Definition Source. I.e., he cannot update the details of the ASCCP. The following business rules are applied:
	1. Min >= 0
	2. Max >= -1 and (Max >= Min when Max != -1)
	3. The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
	4. Min, Max, and Deprecated are required.
	5. A warning should be given when the Definition is empty.
	6. Deprecated must be false and locked (because it is a new association, it shouldn’t be deprecated).
4. The end user can append a BCCP to an ACC that results in an association to the BCCP in the same release in any state. The default value of the new BCC shall be as follows: Min=0, Max = “unbounded”, Deprecated = false and disabled, Entity Type = Element, Value Constraint= None (Default and Fixed value should be empty), Definition = empty, Definition Source = empty.
	1. The selected BCCP can be in any state.
	2. A warning shall be given if the BCCP is deprecated.
	3. The added BCCP shall not cause a property uniqueness violation to the ACC.
	4. The resulting BCC shall be in the WIP state.
5. The end user can right-click on any associations and insert a BCCP before or after the BCCP. The rest of the behavior is the same as test assertion #4.
6. The end user can edit the following detail of a BCC - Min, Max, Entity Type, Default or Fixed Value, Definition, and Definition Source. He cannot update the BCCP information. The following business rules apply:
	1. Min >= 0
	2. Max >= -1 and (Max >= Min when Max != -1)
	3. The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
	4. All fields except Definition and Definition Source are required. However, a warning should be given when the Definition is empty.
	5. Deprecated must be false (because it is a new association, it shouldn’t be deprecated).
	6. The Default and Fixed value shall be disabled and cleared of value if the Entity Type is Element. The system shall warn the user that the Default and Fixed Value will be cleared if changing entity type to Element. If enabled, the Default and Fixed value shall be mutually exclusive.
	7. If the Entity Type is changed from Element to Attribute the Min Cardinality should be changed to 0 and the Max Cardinality to 1.
	8. The Entity Type can be changed to Attribute ONLY if the BCCP has no SC or all SCs have 0 max cardinality.
7. The end user can change (move up or down) the sequence of an association to an ASCCP. It would be good to be able to drag-n-drop instead of moving up or down.
8. The end user can change (move up or down) the sequence of an association to a BCCP. It would be good to be able to drag-n-drop instead of moving up or down.
9. The end user can remove an association (ASCC or BCC) that has no reference, such as, as a replacement association to a deprecated one. There must be a confirmation dialog box though.
10. The developer can add a based ACC to an ACC that is in the same release.
	1. The new based ACC can be in any state.
	2. If the chosen based ACC is deprecated, a warning shall be given.
	3. The based ACC can be only of Base or Semantics component type.
	4. The end user cannot change the fields of the base ACC.
	5. The based ACC should not contain an ASCCP or a BCCP with the same property term as those already in the ACC itself (property uniqueness).
11. The end user can remove the based ACC when one exists.
12. The end user can transfer the ownership of an ACC, which is in WIP states and he owns, to another end user but not developer. In that case the ownership of the associations (ASCC and BCC) are transferred as well.

### Test Step Pre-condition:



### Test Step: