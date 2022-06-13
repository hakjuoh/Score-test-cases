## Test Case 11.2

> Creating a brand-new developer code list

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
On the Code List View/Edit page where a working branch is selected, the developer can create a brand-new code list without base with only required information, See Create a Brand New Code List in Score User Guide for Mandatory/Optional fields. The following are default values – Based Code List = Null and cannot be changed; Name = “a code list”; List ID = Randomly Generated GUID; Agency ID = the OAGI one; Version = 1; Definition = blank; Definition Source= blank; Remark = blank; Deprecated = false (and locked); Namespace = null; Comments = empty. The brand-new CL must not have any release assigned yet, i.e., it must not appear in any release branch except the working branch. It has a revision number 1.

#### Test Assertion #2
The developer can create a code list without base with all information specified and multiple code values. In addition, Code list value cannot be duplicated.

#### Test Assertion #3
The developer can remove a code value during the code list without base creation.

#### Test Assertion #4
The developer cannot create a code list without base, when it does not meet a uniqueness constraint. See Create a Brand New Code List in Score User Guide for the uniqueness constraint.

#### Test Assertion #5
The developer cannot create a CL based on another CL.

#### Test Assertion #6
The developer cannot create a brand-new developer CL when a release branch is selected.

#### Test Assertion #7
Brand new Code List values should not be able to be Unused – the flag should be disabled or hidden.

### Test Step Pre-condition:



### Test Step: