## Test Case 15.14

> Creating a brand-new end user BCCP

Pre-condition: N/A



### Test Assertion:

1. On the CC View/Edit page where a particular release branch is selected, the end user can create a brand-new BCCP by selecting a BDT which can be in any state and belongs to any user. The BDT choice shall, by default, be all BDT types and Commonly Used filter set to Empty-All. (see section 4.1.1.12.1 in the SRT Design Document version 2.4 to understand what is unqualified BDT), but the user has a choice to be able to select any BDT (type > 1). The BCCP should have the following default values – Property Term = “Property Term”; DEN = Property Term + “. “ + BDT_Data_Type_Term and locked; Nillable = false; Deprecated = false and disabled; Value Constraint= None (Default and Fixed value should be empty); Definition = blank; ; Definition Source = blank; Namespace = null, Comments = empty. The brand-new BCCP must have the selected release number assigned right away, i.e., it must not appear in any release except the release the user has selected at the time of creation. It has a revision number of 1. The BCCP should display the associated BDT details but cannot be changed. BDT supplementary components are displayed in the tree but their details cannot be changed.
2. The end user cannot create a brand-new BCCP when the working branch is selected.

### Test Step Pre-condition:



### Test Step: