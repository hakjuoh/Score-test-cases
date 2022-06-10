## Test Case 10.8

> Developer ACC state management

Pre-condition: The user is on the ACC detail page, which he owns.

All these state changes need a confirmation dialog box with slightly different messages.

### Test Assertion:

1. The developer can change the ACC state from WIP to Draft state. The system shall then change the state of its children associations that are also in the WIP state to the Draft state. There is no need to check the state of the dependencies (we will ensure that everything is consistently in the Candidate state at the release time). (Note that I change the rule about viewing details of CC in WIP state that the detail can be viewed by any user so the user should be able to expand the tree of the ACC).
2. The developer can change the ACC state from Draft to Candidate. The system shall then change the state of its children associations that are also in the Draft state to the Candidate state.
3. The developer can retract a candidate ACC. This action put the ACC and all of its association back to the WIP state.
4. The developer can change the ACC state from Draft back to WIP. The system shall then change the state of its children associations also back to WIP.

### Test Step Pre-condition:

1. The following CCs should exist:
2. There are the ACC108a, ASCCP108a and BCCP108a created by the developer of the test case and they are in WIP state.

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the ACC108a and clicks Draft button.
3. The developer confirms its intention in the returned message.
4. Verify that the ACC108a is in Draft state. (Assertion #1)
5. He opens the ASCCP108a and clicks Draft button.
6. The developer confirms its intention in the returned message.
7. Verify that the ASCCP108a is in Draft state. (Assertion #1)
8. He opens the BCCP108a and clicks Draft button.
9. The developer confirms its intention in the returned message.
10. Verify that the BCCP108a is in Draft state. (Assertion #1)
11. He opens the ACC108a and clicks Candidate button.
12. The developer confirms its intention in the returned message.
13. Verify that the ACC108a is in Candidate state. (Assertion #2)
14. He opens the ASCCP108a and clicks Candidate button.
15. The developer confirms its intention in the returned message.
16. Verify that the ASCCP108a is in Candidate state. (Assertion #2)
17. He opens the BCCP108a and clicks Candidate button.
18. The developer confirms its intention in the returned message.
19. Verify that the BCCP108a is in Candidate state. (Assertion #2)
20. He opens the ACC108a and clicks Back to WIP button.
21. The developer confirms its intention in the returned message.
22. Verify that the ACC108a is in WIP state. (Assertion #3)
23. He opens the ASCCP108a and clicks Back to WIP button.
24. The developer confirms its intention in the returned message.
25. Verify that the ASCCP108a is in WIP state. (Assertion #3)
26. He opens the BCCP108a and clicks Back to WIP button.
27. The developer confirms its intention in the returned message.
28. Verify that the BCCP108a is in WIP state. (Assertion #3)
29. He opens the ACC108a and moves it to Draft state. Afterwards, he clicks on the Back to WIP button.
30. The developer confirms its intention in the returned message.
31. Verify that the ACC108a is in WIP state. (Assertion #4)
32. He opens the ASCCP108a and moves it to Draft state. Afterwards, he clicks on the Back to WIP button.
33. The developer confirms its intention in the returned message.
34. Verify that the ASCCP108a is in Draft state. (Assertion #4)
35. He opens the BCCP108a and moves it to Draft state. Afterwards, he clicks on the Back to WIP button.
36. The developer confirms its intention in the returned message.
37. Verify that the BCCP108a is in Draft state. (Assertion #4)