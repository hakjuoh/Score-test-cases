## Test Case 28.1

> BIEs Tab

Pre-condition: N/A



### Test Assertion:

1. In the “Total BIEs by state” panel, the developer can see the number of all BIEs per state.
2. In the “Total BIEs by state” panel, the developer can click on a state to view the BIEs of that state in the BIE List page.
3. In the “My BIEs by state” panel, the developer can see the number of BIEs owned by him per state.
4. In the “My BIEs by state” panel, the developer can click on a state to view the BIEs of that state and owned by him in the BIE List page.
5. In the “BIEs by users and states” panel, the developer can see the number of BIEs per user and per state.
6. In the “BIEs by users and states” panel, the developer can select the user to narrow down the list and see only the number of his BIEs per state.
7. In the “BIEs by users and states” panel, the developer can click on a table cell, which contains the number of BIEs for a user and a state, to view the relevant BIEs into the BIE List page.
8. In the “My recent BIEs” panel, the developer can see the last 5 BIEs that he modified or created.
9. In the “My recent BIEs” panel, the developer can click on a BIE to view it in the Edit BIE page.

### Test Step Pre-condition:

1. There are at least three BIEs created by the OAGi developer and they are in different states (Editing, Candidate, Published).
2. There are at least three BIEs created by an end user and developer (e.g., usera and devx) and they are in different states.

### Test Step:

1. An OAGi developer logins.
2. He visits the Home page and clicks on the BIEs tab.
3. Verify that the “Total BIEs by state” panel contains the number of the BIEs existing in Score per their state (e.g., by first navigating to the BIE List and count them – without using the Database) (Assertion #1)
4. He clicks on the Editing state of the “Total BIEs by state” panel.
5. Verify that the BIE list is returned where all BIEs in Editing state are displayed. Also verify that their number is the same as the number displayed inside the Editing bar of the “Total BIEs by state” panel. Finally, verify that there are BIEs owned by different users (e.g., usera) but not BIEs in Candidate or Published state. (Assertion #2)
6. The developer goes back to home page and clicks the BIEs tab.
7. He clicks on the Candidate state of the “Total BIEs by state” panel.
8. Verify that the BIE list is returned where all BIEs in Candidate state are displayed. Also verify that their number is the same as the number displayed inside the Candidate bar of the “Total BIEs by state” panel.  Finally, verify that there are BIEs owned by different users (e.g., usera) but not BIEs in Editing or Published state. (Assertion #2)
9. The developer goes back to home page and clicks the BIEs tab.
10. He clicks on the Published state of the “Total BIEs by state” panel.
11. Verify that the BIE list is returned where all BIEs in Published state are displayed. Also verify that their number is the same as the number displayed inside the Published bar of the “Total BIEs by state” panel. Finally, verify that there are BIEs owned by different users (e.g., usera) but not BIEs in Editing or Candidate state. (Assertion #2)
12. The developer goes back to home page and clicks the BIEs tab.
13. Verify that the “My BIEs by state” panel contains the number of his BIEs per their state (e.g., by first navigating to the BIE List and count them – without using the Database) (Assertion #3)
14. He clicks on the Editing state of the “My BIEs by state” panel.
15. Verify that the BIE list is returned where the BIEs owned by the developer and are in Editing state are displayed. Also verify that their number is the same as the number displayed inside the Editing bar of the “My BIEs by state” panel. Finally, verify that there is no BIEs owned by another user or developer (e.g., usera or devx) as well as there is no BIEs in Candidate or in Published state. (Assertion #4)
16. The developer goes back to home page and clicks the BIEs tab.
17. He clicks on the Candidate state of the “My BIEs by state” panel.
18. Verify that the BIE list is returned where the BIEs owned by the developer and are in Candidate state are displayed. Also verify that their number is the same as the number displayed inside the Candidate bar of the “My BIEs by state” panel. Finally, verify that there is no BIEs owned by another user or developer (e.g., usera or devx) as well as there is no BIEs in Editing or in Published state. (Assertion #4)
19. The developer goes back to home page and clicks the BIEs tab.
20. He clicks on the Published state of the “My BIEs by state” panel.
21. Verify that the BIE list is returned where the BIEs owned by the developer and are in Published state are displayed. Also verify that their number is the same as the number displayed inside the Published bar of the “My BIEs by state” panel. Finally, verify that there is no BIEs owned by another user or developer (e.g., usera or devx) as well as there is no BIEs in Editing or in Candidate state. (Assertion #4)
22. The developer goes back to home page and clicks the BIEs tab.
23. Verify that the “BIEs by users and states” panel displays the correct number of BIEs per state and per user (e.g., by first counting them using BIE List page and then compare their number to the ones displayed in the “BIEs by users and states” panel) (Assertion #5)
24. The developer clicks on the “User” filter of the “BIEs by users and states” panel and chooses his name.
25. Verify that the “BIEs by users and states” panel displays only the number of the BIEs that he owns. Also, verify that the number of the BIEs per state is correct as well as the Total Number of the BIEs that he owns. (Assertion #6)
26. The developer clicks on the “User” filter of the “BIEs by users and states” panel and chooses another username (e.g., usera)
27. Verify that the “BIEs by users and states” panel displays only the number of the BIEs that the usera owns. Also, verify that the number of the BIEs per state is correct as well as the Total Number of the BIEs that the usera owns. (Assertion #6)
28. The developer clicks on the number of BIEs that exist under the Editing cell of a developer (e.g., “oagi” developer).
29. Verify that the BIE List page is returned where the BIEs onwed by the “oagi” developer are displayed. Also, verify that the number of them is the same as the number that was displayed in the “BIEs by users and states”. Finally, verify that there is no BIE owned by another user or developer (e.g., devx or usera) (Assertion #7)
30. The developer visits the Home page and clicks on BIEs tab.
31. Verify that the “My recent BIEs” contains the last modified BIEs owned by him or the last created BIEs by him. (Assertion #8)
32. The developer clicks on a BIE of the “My recent BIEs” panel.
33. Verify that the “Edit BIE” page is returned where he can view or edit the BIE clicked. (Assertion #9)