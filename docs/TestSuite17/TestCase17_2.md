## Test Case 17.2

> Creating a brand-new end user code list

Pre-condition: A release branch is selected.



### Test Assertion:

1. On the Code List View/Edit page where a release branch is selected, the end user can create a brand-new code list without base with only required information, See Create a Brand New Code List in Score User Guide for Mandatory/Optional fields. The following are default values – Based Code List = Null and cannot be changed; Name = “a code list”; List ID = Randomly Generated GUID; Agency ID = default to the “Mutually Defined” one; Version = blank; Definition = blank; Definition Source= blank; Remark = blank; Deprecated = false (and locked); Namespace = null; Comments = empty. It must not appear in any other branch. It has a revision number 1. There must be no “Extensible” Checkbox.
2. The end user can create a code list without base with all information specified and multiple code values. In addition, Code list value cannot be duplicated.
3. The end user can remove a code value during the code list without base creation.
4. The end user cannot create a code list without base, when it does not meet a uniqueness constraint. See Create a Brand New Code List in Score User Guide for the uniqueness constraint.
5. The end user can create a brand-new code list based on another published developer code list in the same branch.
6. The end user CANNOT create a brand-new CL based on another end-user code list.
7. There is a developer code list that has different revisions in two releases, one of which is the release currently selected by the end user and is a later release. The end user must not be able to create a brand-new code list based on the earlier revision of the developer code list.

### Test Step Pre-condition:



### Test Step: