## Test Case 15.9

> Editing associations during an end-user ACC amendment

Pre-condition: An end-user ACC is opened and its revision is higher than 1.



### Test Assertion:

1. The end user can append an ASCCP to add an ACC that results in a brand-new association to the (developer or end user) ASCCP in the same release in any state. The default value of the new ASCC shall be as follows: Min = 0, Max = “unbounded”, Deprecated = false and disabled, Definition=empty, Definition Source=empty.
	1. The selected ASCCP can be in any state.
	2. A warning shall be given if the ASCCP is deprecated.
	3. The ASCCP shall not violate the property uniqueness constraint of the ACC. In other words, the ACC shall not already contain an ASCCP or BCCP with the same property term whether in itself or within its based ACC. (maybe the ASCCP with the same property term should not appear in the list of the dialog used to append ASCCPs. Note that there may be multiple ASCCPs with the same property term even in the same release – this situation occurs with the Data Area ASCCP).
	4. The resulting ASCC shall be in the WIP state.
	5. If the ASCCP is not reusable, check that there is no ASCC already using it.
2. The end user can right-click on any associations and insert an ASCCP before or after it. The rest of the behavior is the same as test assertion #1.
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
	5. If the Entity Type is changed from Element to Attribute the Min Cardinality should be changed to 0 and the Max Cardinality to 1.
	6. Entity Type can be changed to Attribute only when the BCCP has no SC or all SCs have min and max cardinalities equal zeros.
5. The end user can right-click on any associations and insert a BCCP before or after the BCCP. The rest of the behavior is the same as test assertion #4.
6. The end user can edit the following detail of a new BCC (rev = 1) - Min, Max, Entity Type, Default or Fixed Value, Definition, and Definition Source. He cannot update the BCCP information. The following business rules apply:
	1. Min >= 0
	2. Max >= -1 and (Max >= Min when Max != -1)
	3. The user may type in “unbounded” in place of -1 for Max. If the user type in -1 for Max, the UI should display it as “unbounded”.
	4. All fields except Definition and Definition Source are required. However, a warning should be given when the Definition is empty.
	5. Deprecated must be false (because it is a new association, it shouldn’t be deprecated).
	6. The Default and Fixed value shall be disabled and cleared of value if the Entity Type is Element. The system shall warn the user that the Default and Fixed Value will be cleared if changing entity type to Element. If enabled, the Default and Fixed value shall be mutually exclusive.
7. The end user can change (move up or down) position of the brand-new association to an ASCCP. It would be good to be able to drag-n-drop instead of moving up or down. The existing ASCC cannot be moved. If the user tries to move existing ASCC a dialog box should pop up indicating that “ASCC existed before the amendment cannot be moved.”
8. The end user can change (move up or down) position of the brand-new association to a BCCP. It would be good to be able to drag-n-drop instead of moving up or down. Existing BCC cannot be moved. If the user tries to move existing BCC a dialog box should pop up indicating that “BCC existed before the amendment cannot be moved.”
9. The end user can remove a brand-new association (ASCC or BCC) if the association has no reference, particularly as a replacement of a deprecated association. There must be a confirmation dialog box though.
10. The end user can add a based ACC to an ACC that is in the same release if one does not already exist.
	1. The new based ACC can be in any state.
	2. If the chosen based ACC is deprecated, a warning shall be given.
	3. The based ACC can only be Base or Semantics component type.
	4. The end user cannot change the fields of the base ACC.
	5. The based ACC should not contain an ASCCP or a BCCP with the same property term as those already in the ACC itself (property uniqueness).
11. The end user can remove the based ACC when one already exists before the amendment.
12. The end user can transfer the ownership of an ACC, which is in WIP states and he owns, to another end user. In that case the ownership of the associations (ASCC and BCC) are transferred as well.
13. The end user cannot remove ASSC or BCC existed before the amendment.
14. The end user can make the following changes to ASCC existed before this amendment following these rules.
	1. 0 <= Min <= PreviousMin
	2. If Previous-Max = -1, it cannot be changed; otherwise, Max = -1 or Max >= Previous-Max
	3. If the Deprecated was already True before the amendment, the field along with the Replaced By field should be lock. If it was False before the amendment the checkbox shall be enabled. When Deprecated is changed to True, the developer must be able to select a replacement ASCC or BCC (filtered out the deprecated ones) within the ACC from a drop-down list in the Replaced By field – but the field is optional. If the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.
	4. A warning should be given when the Definition is empty.
15. The end user can cancel the amendment. In such case, all changes to the ACC during the amendment including changes to its associations and based ACC addition are rolled back. The changes made before the cancellation are still kept in the history record.

### Test Step Pre-condition:



### Test Step: