## Test Case 24.1

> Reuse a BIE

Pre-condition: In a latest release, there are existing top-level BIEs in Production, QA, and WIP state that reference the same CC as a BIE under another top-level BIE being edited (we will call these “BIEs to be reused”). There are also some other top-level BIEs in Production state that do not reference that same CC. There are BIEs with the same DENs as “BIEs to be reused” in an older release.

BIE reuse allows for top-level BIEs to be reused under another top-level BIE.

### Test Assertion:

1. For a particular descendant node (reuse-target node) of a top-level BIE in Editing state, the end user can invoke the ‘Reuse BIE’ function.
	1. The reuse-target node can only be ASBIE/ASBIEP/ABIE node but not any BBIE/BBIEP nor SC node. The root top-level BIE node cannot be a reuse-target node.
	2. A confirmation dialog shall appear indicating that “Details of descendant BIEs will be lost. Do you want to continue?”
	3. Top-level BIEs in any state owned by any user (i.e., end user or developer) in the same Release as the top-level BIE that reference the same ASCCP as the target node can be chosen from. (Maybe from the UI the ‘reference the same ASCCP’ assertion can only be partially tested that only ASBIEPs with the same property terms are in the list). The pop-up dialog for choosing a top-level BIE must include the following details – State, Property Term, Business Term, Owner, Business Context, Remark, Version, Status, and Updated Date Time (Release is NOT needed, they must be in the same release as the reuse-target anyway). Filters shall be available for Business Context, Owner, Updater, Updated Date Time. Business Context and Remark may be visible only when hovering over.
	4. An icon indicating a reused BIE shall be present. Clicking on that node shall open the corresponding top-level BIE in another tab.
	5. On the detail pane of a reused BIE node, Business Term, Context Definition, Remark, Version, Owner, Business Contexts of the reused ASBIEP shall be display. The user can still customize cardinality, context definition, nillable details of the ASBIE (which belongs to the reusing top-level BIE). Details of the reused BIE and its descendant nodes cannot be changed. Nillable is editable ONLY if Nillable of the underlying ASCCP is true.
2. The end user can reuse developer top-level BIE.
3. The end user can reuse a BIE that has a nested BIE Reuse. All reuse information shall appear appropriately on the UI.
4. The end user can remove the BIE Reuse. This menu option shall be available ONLY on the reused BIE node. After removal:
	1. Only the ASBIE details remain on the detail pane of the node.
	2. Other children nodes shall be unchecked.
5. The end user cannot discard a reused BIE that he owns if it is used in another top-level BIE (the reusing BIE can be owned by a different user).
6. The end user cannot move a reusing BIE from WIP state to QA state if the reused BIE is in WIP state.
7. The end user cannot move a reusing BIE from QA state to Production state if the reused BIE is in QA state.
8. The end user can move a reusing BIE from WIP state to QA state if the reused BIE is in QA or Production state
9. The end user can move a reusing BIE from QA state to Production state if the reused BIE is in Production state.
10. The end user cannot move a reused BIE from QA state to WIP state if the reusing BIE is in QA state.
11. The end user can move a reused BIE from QA state to WIP state if the reusing BIE is in WIP state.
12. The end user can see the details of a reused BIE node that he does not own, and it is in WIP or QA state. He can also edit the details of the association of the BIE Reuse node.
13. The end user can express a reusing BIE that reuses a BIE in WIP state and owned by a different user.

### Test Step Pre-condition:



### Test Step: