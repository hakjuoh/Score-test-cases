## Test Case 10.22

> Developer BCCP state management

Pre-condition: The user is on the BCCP detail page, which he owns.
All these state changes need a confirmation dialog box with slightly different messages.


### Test Assertion:

#### Test Assertion #1
The developer can change the BCCP state from WIP to Draft.

#### Test Assertion #2
The developer can change the BCCP state from Draft back to WIP.

#### Test Assertion #3
The developer can change the BCCP state from Draft to Candidate.

#### Test Assertion #4
The developer can change the BCCP state from Candidate back to WIP.

### Test Step Pre-condition:

1. There is a BCCP, say BCCP4, which is in WIP state with revision number 1.
2. The working branch is selected

### Test Step:

1. An OAGi developer logs into the system.
2. He opens the BCCP4 and sets it to Draft state while he confirms his intention.
3. Verify that the BCCP4 is in Draft state. (Assertion [#1](#test-assertion-1))
4. He sets BCCP4 back to WIP again while he confirms his intention.
5. Verify that the BCCP4 is in WIP state. (Assertion [#2](#test-assertion-2))
6. He sets the BCCP4 to Draft and then to Candidate state while he confirms his intention.
7. Verify that the BCCP4 is in Candidate state. (Assertion [#3](#test-assertion-3))
8. He opens the BCCP4 and sets it back to WIP state while he confirms his intention..
9. Verify that the BCCP4 is in WIP state. (Assertion [#4](#test-assertion-4))