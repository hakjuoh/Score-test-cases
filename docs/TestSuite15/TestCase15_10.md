## Test Case 15.10

> Creating a brand-new end user ASCCP

Pre-condition: N/A



### Test Assertion:

1. The end user cannot create a brand-new ASCCP when the working branch is selected.
2. On the CC list page where a release branch is selected, the end user can create a brand-new ASCCP by selecting an (developer or end user) ACC in the same release, in any state, and owned by any user. The ASCCP should have the following default values – Property Term = [ACC Object Class Term]; DEN = [Property Term] + [ACC Object Class Term] and locked; Reusable = true; Definition = blank; Definition_Source=blank; Deprecated = false and disable; Nillable = false; Namespace = null; Comments = empty. The brand-new ASCCP must have the selected release number assigned right away, i.e., it must not appear in any other release except the release the user has selected at the time of creation. It has a revision number of 1. The ASCCP should have the associated ACC along with its properties but they cannot be changed. Only ACC whose Component Type is Semantics or Semantic Group can be selected.
3. If the underlying ACC has changed, particularly the Object Class Term of the ACC, after the ASCCP was first created, the system should automatically pick up the change, e.g., when the ASCCP is opened or refreshed on the ASCCP details page.
4. The end user can create an ASCCP from an ACC in WIP state using the function “Create ASCCP from this”. The Property Term of the created ASCCP is based on the Object Class Term of the ACC.

### Test Step Pre-condition:



### Test Step: