## Test Case 10.18

> Creating a brand-new developer BCCP

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
On the CC list page where a working branch is selected, the developer can create a brand-new BCCP by selecting a BDT which can be in any state and belongs to any developer. The BDT choice shall be, by default, is empty. Filtering field is used to filter the commonly-used BDT (BDTs may also be classified as Default, Qualified, and Unqualified - see section 4.1.1.12.1 in the SRT Design Document version 2.4 to understand what is unqualified BDT ), but the user has a choice to be able to select any BDT (type > 1). The BCCP should have the following default values – Property Term = “Property Term”; DEN = “Property Term. “ + BDT_Data_Type_Term and disable; Nillable = false; Deprecated = false and disabled; Value Constraint= None (Default and Fixed value should be empty); Definition = blank; Definition Source = blank; Namespace = null, Comments = empty. The brand-new BCCP must not have any specific release assigned yet, i.e., it must not appear in any release branch except the working branch. It has a revision number 1. The BCCP should have the associated BDT details but cannot be changed. BDT supplementary components are displayed in the tree but their details cannot be changed.

#### Test Assertion #2
The developer cannot create a brand-new BCCP when a release branch is selected.

### Test Step Pre-condition:



### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC page and click the “Create BCCP” button.
3. He chooses a BDT to create a BCCP.
4. Verify that all the fields and their defaults values exist. Also, verify that he cannot change the values of the BDT fields. (Assertion [#1](#test-assertion-1))
5. He visits the CC page again.
6. He selects a release branch (e.g., 10.6)
7. Verify that there is no “Create BCCP” button. (Assertion [#2](#test-assertion-2))