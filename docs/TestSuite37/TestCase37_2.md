## Test Case 37.2

> Creating a brand-new end user Agency ID list

Pre-condition: A release branch is selected.

### Test Assertion:

#### Test Assertion #1
On the Agency ID list View/Edit page where a release branch is selected, the end user can create a brand-new Agency ID list without base with only required information, See Create a Brand new Agency ID list in Score User Guide for Mandatory/Optional fields. The following are default values – Based Code List = Null (this field can be hidden in case of an Agency ID list without base) and cannot be changed; Name = “AgencyIdentification”; List ID = Randomly Generated GUID; Agency ID =blank ; Version = blank; Definition = blank; Deprecated = false (and locked); Namespace = null; Comments = empty. It must not appear in any other branch. It has a revision number 1.

#### Test Assertion #2
The end user can create an Agency ID list without base with all information specified and multiple Agency ID list values. In addition, Agency ID list value cannot be duplicated.

#### Test Assertion #3
The end user can discard an Agency ID list value during the Agency ID list without base creation.

#### Test Assertion #4
The end user cannot create an Agency ID list without base, when it does not meet a uniqueness constraint (i.e., no other Agency ID list with same List ID, Agency ID and Version should exist in the selected branch). See Create a Brand New Agency ID List in Score User Guide for the uniqueness constraint.

#### Test Assertion #5
The end user can create a brand-new Agency ID list based on another published developer code list. The developer Agency ID list must be in the same release as the selected release branch.

#### Test Assertion #6
The end user CANNOT create a brand-new Agency ID list based on another end-user code list.

#### Test Assertion #7
There is a developer Agency ID list that has different revisions in two releases, one of which is the release currently selected by the end user and is a later release. The end user must not be able to create a brand-new Agency ID list based on the earlier revision of the developer Agency ID list.

#### Test Assertion #8
The value in the Agency ID field must be one of the IDs in the list.

### Test Step Pre-condition:



### Test Step: