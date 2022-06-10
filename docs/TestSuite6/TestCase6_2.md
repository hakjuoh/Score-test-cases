## Test Case 6.2

> End user authorized management of BIE

Pre-condition: N/A



### Test Assertion:

1. The end user can invoke a local extension when the BIE is in WIP state and there is no corresponding UEGACC (user extension group ACC) in WIP or QA state. The UEGACC shall have an incremental revision number.
2. When the end user invokes a local extension and the corresponding UEGACC is in WIP or QA state and the user is not the current owner of the UEGACC, display a dialog indicating “The core component is being extended by “ + [the owner of the UEGACC] or similar. If the UEGACC is in QA state, the end user can view its details but cannot make any change.
3. When the end user invokes a local extension and the corresponding UEGACC is in WIP or QA state and the user is the current owner of the UEGACC, open the UEGACC.
4. When the end user expands the Extension node of a BIE and there is a corresponding UEGACC not in Production state, the UI must grey out and make all the associations (and their descendants) added to the UEGACC uneditable.
5. When the end user expands the Extension node of a BIE and there is a corresponding UEGACC in Production state but:
	1. It has child association to an end user ASCCP which is not in Production state, that child node and all its descendants shall be greyed out and uneditable.
	2. It has a child association to an end user ASCCP that is in the Production state, but the end user ACC (of the ASCCP) is not in the Production state. That child node and all of its descendants shall be greyed out and uneditable.
	3. It has child association to an end user BCCP which is not in Production state, that child node and all its descendants shall be greyed out and uneditable.
	4. It has a child association to an end user ASCCP that is in the Production state. The end user ACC of the ASCCP is also in the Production state and was amended. The ACC has a child ASCC that points another end user ASCCP2 that is not in the Production state. That ASCC/ASCCP2 node shall be grey out and uneditable.
	5. It has a child association to an end user ASCCP that is in the Production state. The end user ACC of the ASCCP has a Group component type and is NOT in the Production state. Either NO children of that group ACC shall be visible, or all children shall be grey out and uneditable.
6. Do all previous again targeting the same BIE and BIE extension but use another release. Make sure to introduce some revisions in the CCs used by the BIE, BIE extension point, and the UEGACC. Even use the EUCC with the same name but different slightly different content. In addition to verifying 5.1 to 5.5, verify that the expected differences between revisions are there.
7. Apply test assertion 1 to 5 to the global extension except appending an ASCCP to the global extension. Test also that an ASCCP cannot be appended to the global extension.
8. A code list which is an extension of a default code list (aka compatible code lists) used by a BBIE must show up for the code list selection, when the Value Domain Type is set to “Code”. Specifically:
	1. Only production, compatible code lists in the same release as the BIE shall be included, i.e., a code list exists only in a newer release shall not be included.
	2. Compatible end user code lists in the same release as the BIE shall be included. However, if it is in the WIP or QA state, flag that the code list is being changed (maybe use dark yellow and italicized font – yellow like a warning light) (the meaning is the code list is usable but unstable. If the user express BIE, the result is in the limbo status). If the code list is in Deleted state use Strikethrough font.
	3. If there is no default code list, all developer code lists in the published state in the same release and end user code lists in the same release shall be included. End user code lists shall be displayed in the same way as described in 8.2.
9. End user cannot create a new BIE from an ASCCP whose ACC has a group component type.
10. The end user can click the Detail Reset button of a specific BIE node to initial the values of the BIE node. These values are based on the corresponding CC of the BIE node. A confirmation dialog should be also returned in order for the end user to confirm his intension of resetting the BIE node values.
11. The end user can Exclude SCs or not from the Searching Field by checking or unchecking the “Exclude SCs” checkbox accordingly.
	1. If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
	2. If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field
12. The end user can create a BIE from an end user ASCCP providing that it is in Production state. Check that the end user can create BIEs from both ASCCP that he owns or not.
13. The end user cannot create a new BIE from an ASCCP whose ACC has a group component type.
14. The end user can edit the BIE if the end user ASCCP is in Production State
	1. If the end user ASCCP is amended (i.e., moved to WIP state), the BIE cannot be edited. The fields of the BIE nodes are disabled including the “Used” checkbox.
	2. If the end user ASCCP is moved to the QA state, the BIE cannot be edited. The fields of all BIE nodes (ancestors and descendants) are disabled including the “Used” checkbox.
	3. If the end user ASCCP is moved to the Deprecated state (i.e., it is deprecated), flag the root node of the BIE to indicate that status.
	4. If any of the nodes of the base ACC of the ASCCP is not in Production state, their corresponding BIE nodes cannot be edited. Check the base ACC of the base ACC of the ASCCP. Also check an ASCCP and BCCP node of the base ACC of the base ACC of the ASCCP.
	5. If the corresponding CC of a BIE node is Deleted, the BIE node cannot be edited. It can be also flagged as deleted.
	6. If any child or descendant properties are from group and the group is not in Production state, those properties have to be locked in the BIE.

### Test Step Pre-condition:



### Test Step: