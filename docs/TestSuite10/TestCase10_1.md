## Test Case 10.1

> Core component access

Pre-condition: A working branch is selected.
(As it is now) individual ASCC page is not provided.

### Test Assertion:

#### Test Assertion #1
The developer can see in the CC list page all CCs owned by any developer in any state.

#### Test Assertion #2
The developer can view and edit the details of a CC that is in WIP state and owned by him.

#### Test Assertion #3
The developer CAN view but CANNOT edit the details of a CC that is in WIP state and owned by another developer. However, he can add comments.

#### Test Assertion #4
The developer can view the details of a CC that is in Draft, Candidate, or Release Draft state and owned by any developer but he cannot make any change except adding comments.

#### Test Assertion #5
The developer can view the details of a Published CC owned by any developer but he cannot make any change except adding comments or make a new revision of the CC.

#### Test Assertion #6
There must not be any end user CC or User Extension Group CC listed in the Working branch.

#### Test Assertion #7
The developer can view details of a deleted CC owned by another developer.

#### Test Assertion #8
The developer cannot edit details of a deleted CC owned by him. He can add comments.

#### Test Assertion #9
The developer cannot edit details of a deleted CC owned by another developer. He can add comments.

#### Test Assertion #10
The developer can filter Core Components based on the branch.

#### Test Assertion #11
The developer can filter Core Components based on their Type.

#### Test Assertion #12
The developer can filter Core Components based on their State.

#### Test Assertion #13
The developer can filter Core Components based on their Updated Date.

#### Test Assertion #14
The developer can search for Core Components based only on their DEN, particularly when using the exact search with double quotes, only DEN containing exact match should return. For example, test this with “identifier group”, the result (of ACC search) shall be totally different from “identifiers group”.

#### Test Assertion #15
The developer can search for Core Components based only on their Definition, particularly when using the exact search with double quotes, only definition containing exact match should return. For example, test this with “Actual Ledger”, the result (of ASCCP search) shall be totally different from “Ledger Actual”.

#### Test Assertion #16
The developer can search for Core Components based only on their Module.

#### Test Assertion #17
The developer can search for Core Components based only on their Component Type.

#### Test Assertion #18
The developer can short Core Component based on the Den column.

#### Test Assertion #19
The developer can move states of several CCs in one shot on the view/edit CC page. Test for:

	1. Changing state from WIP to Draft
	2. Changing state from Draft to WIP
	3. Changing state from Draft to Candidate
	4. Transfer the ownership
	5. Deleting.

#### Test Assertion #20
The developer can open a CC and find the usages of its nodes (i.e., ACC, ASCCP or BCCP) by invoking the function “Where Used” of the context menu of a particular node. In the returned dialog, he can view where the CC wherein the selected CC is used. Check the usages for ACC, ASCCP and BCCP nodes.

	1. If an ACC is selected to view wherein it is used, then the ACCs which are based on this ACC either directly or indirectly should be listed in the returned dialog.

### Test Step Pre-condition:

1. There are the following core components:
2. ACCxw, ASCCPxw, BCCPxw created by the developer devx and they are in WIP state
3. ACCxd, ASCCPxd, BCCPxd created by the developer devx and they are in Draft state.
4. ACCxc, ASCCPxc, BCCPxc created by the developer devx and they are in Candidate state.
5. ACCxdel, ASCCPxdel, BCCPxdel created by the developer and be deleted.
6. ACCow, ASCCPow, BCCPow created by the developer oagis and they are in WIP state.
7. ACCod, ASCCPod, BCCPod created by the developer oagis and they are in Draft state.
8. ACCoc, ASCCPoc, BCCPoc created by the developer oagis and they are is Candidate state.
9. …to be expanded when the release is done

### Test Step:

1. The oagis developer logs into Score.
2. The visits the CC page.
3. Verify that he can view in the returned list all the CCs mentioned in the precondition section. (Assertion [#1](#test-assertion-1))
4. The developer clicks on the ACC0w.
5. Verify that he can view and edit it. (Assertion [#2](#test-assertion-2))
6. The developer goes back to the CC list page and clicks on ASCCP0w.
7. Verify that he can view and edit it. (Assertion [#2](#test-assertion-2))
8. The developer goes back to the CC list page and clicks on BCCP0w.
9. Verify that he can view and edit it. (Assertion [#2](#test-assertion-2))
10. The developer goes back to the CC list page and clicks on ACCxw.
11. Verify that he can view it, but he cannot edit it.  (Assertion [#3](#test-assertion-3))
12. He clicks the comment button.
13. Verify that he can view the comments, but he cannot add one. (Assertion [#3](#test-assertion-3))
14. The developer goes back to the CC list page and clicks on ASCCPxw.
15. Verify that he can view it, but he cannot edit it. (Assertion [#3](#test-assertion-3))
16. He clicks the comment button.
17. Verify that he can view the comments, but he cannot add one. (Assertion [#3](#test-assertion-3))
18. The developer goes back to the CC list page and clicks on BCCPxw.
19. Verify that he can view it, but he cannot edit it. (Assertion [#3](#test-assertion-3))
20. He clicks the comment button.
21. Verify that he can view the comments, but he cannot add one. (Assertion [#3](#test-assertion-3))
22. The developer goes back to the CC list page and clicks on ACCxd.
23. The developer makes a comment to the CC.
24. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
25. The developer goes back to the CC list page and clicks on ASCCPxd.
26. The developer makes a comment to the CC.
27. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
28. The developer goes back to the CC list page and clicks on BCCPxd.
29. The developer makes a comment to the CC.
30. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
31. The developer goes back to the CC list page and clicks on ACCxc.
32. The developer makes a comment to the CC.
33. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
34. The developer goes back to the CC list page and clicks on ASCCPxc.
35. The developer makes a comment to the CC.
36. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
37. The developer goes back to the CC list page and clicks on BCCPxc.
38. The developer makes a comment to the CC.
39. Verify that he cannot edit the CC, but the comment has been successfully made. (Assertion [#4](#test-assertion-4))
40. ……to be expanded after release management.
41. The developer visits the CC list page and clicks on ACCxdel.
42. Verify that he can view its details. (Assertion [#7](#test-assertion-7))
43. The developer visits the CC list page and clicks on ASCCxdel.
44. Verify that he can view its details. (Assertion [#7](#test-assertion-7))
45. The developer visits the CC list page and clicks on BCCPxdel.
46. Verify that he can view its details. (Assertion [#7](#test-assertion-7))