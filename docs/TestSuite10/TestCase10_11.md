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
5. Verify that the default values of the ASCCP are those mentioned in Assertion [#1](#test-assertion-1).
6. The developer visits the CC list page, opens the ACC1011ow and changes its Object Class Term.
7. He then opens the brand new ASCCP created in the second test step.
8. Verify that the DEN of the ASCCP has been changed according to the ACC1011ow change. (Assertion [#2](#test-assertion-2))
9. The developer visits CC List page and selects the working branch.
10. Verify that the ASCCP has a revision number 1 and it is listed. (Assertion [#1](#test-assertion-1))
11. The developer visits CC List page and selects a non-working branch.
12. Verify that the ASCCP is not listed. (Assertion [#1](#test-assertion-1))
13. Verify that the button used to create an ASCCP is not displayed. (Assertion [#3](#test-assertion-3))