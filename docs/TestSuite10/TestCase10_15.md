## Test Case 10.15

> Developer ASCCP state management

Pre-condition: The user is on the ASCCP detail page, which he owns.

All these state changes need a confirmation dialog box with slightly different messages. Changing to the Draft state only need a confirmation. Retracting a Candidate ASCCP to WIP needs a confirmation.

### Test Assertion:

1. The developer can change the ASCCP state from WIP to Draft.
2. The developer can change the ASCCP state from Draft back to WIP.
3. The developer can change the ASCCP state from Draft to Candidate.
4. The developer can retract an ASCCP which is in Candidate state back to the WIP state.

### Test Step Pre-condition:

1. There are the following CCs:
2. ACC11015ow that is owned by the developer conducting the test steps and is in WIP state.
3. ASCCP11015ow that is owned by the developer conducting the test steps, is in WIP state and uses the ACC11015ow.
4. ASCCP21015ow that is owned by the developer conducting the test steps and is in WIP state.

### Test Step:

1. An OAGi developer logs into the system.
2. He visits the CC list page and clicks to view ASCCP21015ow.
3. He moves the ASCCP21015ow to the Draft state and he confirms his intension to a returned message.
4. Verify that the is in Draft state. (Assertion #1)
5. The developer visits the CC list page and clicks to view ASCCP11015ow.
6. He moves the ASCCP11015ow to the Draft state and he confirms his intension to a returned message.
7. Verify that a message asking him if he wishes to move the ACC11015ow to the Draft state as well. (Assertion #1)
8. He provides his permission for this.
9. Verify that the ACC11015ow is in Draft state. (Assertion #1)
10. The developer visits the CC list page and clicks to view ASCCP21015ow.
11. He moves the ASCCP21015ow back to WIP state while he confirms his intension to a message returned.
12. Verify that the is ASCCP21015ow in WIP state. (Assertion #2)
13. The developer moves the ASCCP21015ow to the Draft state and then to the Candidate while he confirms his intension to do so to a returned message.
14. Verify that the ASCCP21015ow is in Candidate state. (Assertion #3)
15. The developer visits the CC list page and clicks to view ASCCP11015ow.
16. He moves it to the Candidate state and confirms its intension to a returned message.
17. Verify that a message asking him if he wishes to move the ACC11015ow to the Candidate state as well. (Assertion #3)
18. He provides his permission for this.
19. Verify that the ACC11015ow is in Candidate state. (Assertion #3)
20. The developer visits the CC list page and opens the ASCCP21015ow.
21. He moves it back to WIP state (i.e., he retracts it) and he confirms its intention to a returned message.
22. Verify that the ASCCP21015ow is in WIP state. (Assertion #4)