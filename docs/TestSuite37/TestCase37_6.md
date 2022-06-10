## Test Case 37.6

> Deleting an Agency ID list

Pre-condition: N/A

Delete an Agency ID list means that it is marked as “Deleted” and it is still displayed in the Agency ID list page (Core Component -> View/Edit Agency ID list) when the release branch the Agency ID list belongs to is selected. If an Agency ID list is “Deleted” any other end user can restore it.

### Test Assertion:

1. If an end user Agency ID list revision number is 1, the end user owner can delete it when it is in WIP state and is owned by him. A confirmation dialog box should appear to ask for a confirmation.  After successful deletion, the system takes the user back to the View/Edit Agency ID list page with the same release branch selected.
2. End user Agency ID list whose revision number is more than 1 in any state cannot be deleted, check particularly the WIP state.

### Test Step Pre-condition:



### Test Step: