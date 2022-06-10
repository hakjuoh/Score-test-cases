## Test Case 11.1

> Code list access

Pre-condition: A working branch is selected.



### Test Assertion:

1. The developer can see in the View/Edit Code List page all code lists (CLs) owned by any developer in any state.
2. The developer can view and edit the details (including code values) of a CL that is in the WIP state and owned by him.
3. The developer CAN view but CANNOT edit the details of a CL that is in WIP state and owned by another developer.
4. The developer can view the details of a CL that is in Draft, Candidate, Deleted, or Release Draft state and owned by any developer but he cannot make any change except adding comments.
5. The developer can view the details of a Published CL owned by any developer but he cannot make any change except adding comments or make a new revision of the CL.
6. There must not be any end user CL listed in the Working branch.
7. The developer can view details of a deleted code list owned by another developer.
8. A developer can add comments to any developer CL in any state.
9. An end user can add comments to any developer CL in any state.
10. The developer can filter CLs based on the branch.
11. The developer can filter CLs based on deprecation status.
12. The developer can filter CLs based on their State.
13. The developer can filter CLs based on their Updated Date.
14. The developer can search for CLs based only on their Name.
15. The developer can search for CLs based only on their Definition.
16. The developer can search for CLs based only on their Module.

### Test Step Pre-condition:



### Test Step: