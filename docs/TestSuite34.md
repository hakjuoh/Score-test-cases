# Test Suite 34


## Test Case 34.1

> Agency ID access

Pre-condition: A working branch is selected.


### Test Assertion:

#### Test Assertion #1
The developer can see in the View/Edit Agency ID List page all Agency ID Lists owned by any developer in any state.

#### Test Assertion #2
The developer can view and edit the details (including Agency ID List values) of an Agency ID List that is in the WIP state and owned by him.

#### Test Assertion #3
The developer CAN view but CANNOT edit the details of an Agency ID List that is in WIP state and owned by another developer.

#### Test Assertion #4
The developer can view the details of an Agency ID List that is in Draft, Candidate, Deleted, or Release Draft state and owned by any developer but he cannot make any change except adding comments.

#### Test Assertion #5
The developer can view the details of a Published Agency ID List owned by any developer but he cannot make any change except adding comments or make a new revision of the Agency ID List.

#### Test Assertion #6
There must not be any end user Agency ID List listed in the Working branch.

#### Test Assertion #7
The developer can view details of a deleted Agency ID List owned by another developer.

#### Test Assertion #8
A developer can add comments to any developer Agency ID List in any state.

#### Test Assertion #9
An end user can add comments to any developer Agency ID List in any state.

#### Test Assertion #10
The developer can filter Agency ID Lists based on the branch.

#### Test Assertion #11
The developer can filter Agency ID Lists based on deprecation status.

#### Test Assertion #12
The developer can filter Agency ID Lists based on their State.

#### Test Assertion #13
The developer can filter Agency ID Lists based on their Updated Date.

#### Test Assertion #14
The developer can search for Agency ID Lists based only on their Name.

#### Test Assertion #15
The developer can search for Agency ID Lists based only on their Definition.

#### Test Assertion #16
The developer can search for Agency ID Lists based only on their Module.

### Test Step Pre-condition:



### Test Step:

## Test Case 34.2

> Creating a brand-new developer Agency ID List

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
The developer cannot create a brand-new Agency ID List.

### Test Step Pre-condition:



### Test Step:

## Test Case 34.3

> Creating a new revision of a developer Agency ID List

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
On the Agency ID List Detail page of the working branch, the developer can create a new revision of a published Agency ID List regardless of the current owner. The result is that the working branch has that Agency ID List with an incremental revision number that is in the WIP state.  Its detail attributes are initially the same as those of the previous revision. All the Agency ID List Values from the previous revisions shall be present.

### Test Step Pre-condition:



### Test Step:

## Test Case 34.4

> Editing a revision of a developer Agency ID List

Pre-condition: The Agency ID List under test has revision number greater than 1 and is in WIP state.


### Test Assertion:

#### Test Assertion #1
The developer can change the properties of the Agency ID List and save changes with the following business rules.

##### Test Assertion #1.a
The Name, List ID, Agency ID and Namespace cannot be updated.
##### Test Assertion #1.b
Only Version, Definition and Definition Source can be updated.
##### Test Assertion #1.c
The combination of List ID, Agency ID and Version have to be unique in the working branch.

#### Test Assertion #2
Existing Agency ID List Values from the previous revisions cannot be discarded. Only their Meaning, Definition and Definition Source can be changed. If the Deprecated was already True in the previous revision, the field along with the Replaced By field should be locked. If Deprecated was false in the previous revision, the value can be deprecated. When the deprecated is changed from false to true, the developer can select one of Agency ID List Values as a replacement. When the Deprecated is changed to False, the Replaced By field shall be Null and optionally disappears from the UI.

#### Test Assertion #3
A new unique Agency ID List Value can be added and all of its details can be edited, namely the Name and Definition fields. The deprecated field should be disabled because it is a new value.

#### Test Assertion #4
The system shall not allow a new Agency ID List Value that is a duplicate value within the Agency ID List; its name should be unique.

#### Test Assertion #5
A brand-new Agency ID List Value added in this revision can be discarded if it is not a replacement of a deprecated value. A dialog should tell the developer when the value cannot be removed because it is a replacement of a deprecated Agency ID List Value.

#### Test Assertion #6
The developer can cancel the revision. In this case, the system rollbacks the Agency ID List to the previous revision and its children Agency ID List Values back to the previous revision; The system also discard Agency ID List Values added in this revision. The changes made before cancellation are in the history record.

### Test Step Pre-condition:



### Test Step:

## Test Case 34.5

> Developer Agency ID List state management

Pre-condition: The developer is on the Agency ID List detail page, which he owns.
All these state changes need a confirmation dialog box “Do you want to change state of the Agency ID List to XYZ?”.


### Test Assertion:

#### Test Assertion #1
The developer can change the Agency ID List state from WIP to Draft.

#### Test Assertion #2
The developer can change the Agency ID List state from Draft back to WIP.

#### Test Assertion #3
The developer can change the Agency ID List state from Draft to Candidate.

#### Test Assertion #4
The developer can change the Agency ID List state from Candidate back to WIP.

### Test Step Pre-condition:



### Test Step:

## Test Case 34.6

> Deleting an Agency ID List

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
A developer Agency ID List cannot be deleted regardless of its state since its revision number is more than 1.

### Test Step Pre-condition:



### Test Step: