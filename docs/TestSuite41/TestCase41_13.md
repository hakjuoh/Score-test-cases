## Test Case 41.13

> Deleting end user DT

Pre-condition: N/A

Delete a CC means that it is marked as “Deleted” and it is still displayed in the CC list when a non-working branch is selected. If a CC is “Deleted” any other end user can restore it. Delete also means the deleted information is kept in the DT table. Generally, when an entity is opened that has a relationship (whether in association or in base relationship) to a deleted entity, the opened entity shall be flagged as in an invalid state. And once the user has expanded the tree down to the deleted entity, the deleted entity should be flagged as deleted. This is applied to all test cases related to deletions.

### Test Assertion:

1. If an DT revision number is 1, the end user owner can delete it when it is in WIP state. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the CC list page. The deleted DT shall appear in the non-working branch CC list (even without the Deleted state filter).
2. Upon opening a DT that uses a deleted DT as a base, the system shall be able to flag that the opening DT is in an invalid state and flag that the descendant-based DT is in the deleted state. After the based DT is replaced or restored, the end user should be able to see that reflected in the DT tree (e.g., after clicking refresh).
3. DT whose revision number is more than 1 and is in any state cannot be deleted.

### Test Step Pre-condition:



### Test Step: