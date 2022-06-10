## Test Case 19.1

> Release management

Pre-condition: N/A



### Test Assertion:

1. The developer can create a release. The following information can be specified. Release Number, Release License, Release Note, Release Namespace. Release Number and Namespace are required. Once the release is created, it is in the Initialized state – we can call it Initialized Release. There can be multiple Initialized Releases at a particular point in time.
2. The developer can discard a release that is in the Initialized state if there is no reference to it (e.g., modules).
3. From the Initialized Release, a Release Draft can be created by a developer – Create a Release Draft function. There can be only one Release Draft at a particular point in time. I.e., when a Release Draft is being created, another developer MUST NOT be able to invoke the Create a Release Draft function; and when there is a Release Draft, another Release Draft cannot be created. The process of creating a release draft has the following steps.
	1. The developer can add CCs in the working branch that are in the Candidate state (no CCs in other states are allowed) to the release draft (this can include new and revised CCs).
	2. The developer can invoke Validate to:
	3. Validate References. This is an Error validation. The system ensures that those new and revised CCs reference CCs that are included in the release and that are in Candidate or Published state. The following references should be validated 1) ASCCP to ACC, 2) ACC to ASCCP in its ASCC, 3) ACC to BCCP in its BCC, 4) BDT to Code List, 5) BCCP to BDT, 6) BDT to Agency ID List, 7) ACC to based ACC, 8) ACC to replaced-by ACC, 9) ASCCP to replaced-by ASCCP, 10) BCCP to replaced-by BCCP. If the target entity is not in the prior release or the release assignment, the validation fails. If the validation fail, the system shall list CCs that have invalid references and list those CCs that are needed to make the release draft valid. Missing CCs must be listed along with the current state and owner (needed CCs may be in Draft, WIP, or Deleted state or in Candidate state but not included in the release assignment). Optionally, the developer can notify (via email) to the owners of those needed CCs that they need to act upon those CCs so that the release draft can be created. The developer can open the detail page of a needed CC (in another tab), in which actions can be performed based on his ownership and state of the CC. The system shall also give warnings for ACC, ASCCP, BCCP, Code List, Agency ID List and DT revised and used by the CCs in the release assignment, but not included in the release assignment.
	4. Validate Extension. This is a Warning validation. Give a warning:
	5. “Warning! This ACC with “ + [ACC Identity] ” should have an Extension component but it does not.”, if an ACC whose Component Type is Semantics and does not have an association to an ASCCP with DEN = “Extension. ” + [ACC Object Class Term] + “ Extension”. [ACC Identity] is “DEN” + DEN + “ and GUID ” + GUID.
	6. “Warning! This ACC with “ + [ACC Identity] “ has an Extension component but it is not in the last association.”, if an ACC whose Component Type is Semantics, has an association to an ASCCP with DEN = “Extension. ” + [ACC Object Class Term] + “ Extension”, but the ASCCP is not in the last association.
	7. “Warning! This ACC with “ + [ACC Identity] + “ should not have an Extension component.”, if an ACC whose Component Type is not Semantics and has an association to an ASCCP whose Property Term is “Extension”.
	8. Validate Deprecation. This is an Error Validation. New entities that are added to the release and that have its deprecated flag equal to True, need to be checked for references associated with the replacements. The replacement entities must be included in the release. If not, the validation shall report an error.
	9. Validate non-reusable ASCCP. It is an error if a non-reusable ASCCP is used in an ASCC more than one time. (note: this validation is needed because the user may change the reusable to false after already using the ASCCP multiple times.)
	10. If the reference validation fails, the developer can cancel the release draft creation. He can include addition CCs, excludes CC in the release draft, or run the reference validation again (maybe he owns all of the needed CCs and can advance them to the Candidate state).
	11. If the reference validation is successful, the user can hit the Finish button. The system creates a release manifest. The system takes the developer back to the Release page.
4. Initialized Releases shall not show up in the Branch drop down box in the Core Component page or when selecting an ASCCP while creating a BIE.
5. While a release draft is being created, all working branch CCs in the Candidate State that are included in the release draft shall be locked. This is needed so that no one can go in and change states of CCs included in the release draft. So, if anyone has a candidate developer CC already open, they cannot make a commit/change the state, for example, back to WIP.
6. The created Release Draft shall show up in the Branch drop down box in the Core Component page, so that any users can view the CCs. All CCs shall display the Release Draft state. No actions can be performed in this branch except viewing details of those release draft CCs. The Working branch can still show. Among others, it would include CCs in Release Draft state where no actions can be performed except viewing.
7. Release draft shall also not show up when selecting a Release for an ASCCP when creating a BIE.
8. A developer can discard a release draft, i.e., take the release back to the Initialized state. There must be a confirmation dialog. All CCs that were in the Release Draft state shall be set back to the Candidate state. The release manifest of that release shall be cleared.
9. A developer can move a release draft into the published state. There must be a confirmation dialog. All the CCs in the Release Draft state shall be moved the Published state. Afterward, the release shall appear in the branch drop down box on the CC View/Editing page. At this point the history records related to new and changed CCs in that release should be tagged with the release ID (I think based on this information, the system can list the new and changed CCs in the release. This page can be brought up after clicking the Release Name in the Manage Release page. On that page, a link can also be provided to pull up history records related to a particular CC. This can be a future feature).
10. While a release in the draft state, a developer can still update its details including Release Number, Release License, Release Note, Release Namespace. Release Number and Release Namespace are required.
11. After the release is published no further action can be done to the release.
12. End users cannot manage releases, i.e., cannot initialize a release and move it forward through the process.
13. End users can view the list of releases and individual details.

### Test Step Pre-condition:



### Test Step: