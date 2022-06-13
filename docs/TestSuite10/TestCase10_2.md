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
3. Verify that the default values of the ACC are those mentioned in Assertion [#1](#test-assertion-1)
4. The developer visits CC List page and selects a release branch.
5. Verify that the new ACC is not displayed. (Assertion [#1](#test-assertion-1))
6. Verify that there is no “Create ACC” button. (Assertion [#2](#test-assertion-2))