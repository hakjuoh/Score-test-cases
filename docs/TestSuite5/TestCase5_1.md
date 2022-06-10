## Test Case 5.1

> OAGIS developer's authorized management of context categories

Pre-condition: N/A



### Test Assertion:

1. The developer can create a context category with only required information. See Create a Context Category in Score User Guide for Mandatory/Optional fields.
2. The developer can create a context category with all information specified.
3. The developer cannot create a context category with missing required information.
4. The developer can see, in the context category list, all context categories created by any user.
5. The developer can see/edit a context category created by any user.
6. The developer can update a context category with only required information.
7. The developer can update a context category with all information specified.
8. The developer cannot update a context category with missing required information.
9. The developer can discard context categories created by any user provided that there is no context scheme referencing it.
10. The developer cannot discard a context category that has a context scheme referencing it. The system shall indicate context schemes referencing the context category when the developer tries to delete the context category.
11. The search feature is at least working.
12. The developer can select a Context Category from the Context Category List page, navigate through the pages of the paginator while the forenamed Context Category remains selected.

### Test Step Pre-condition:

1. There are context categories already created by various end users, say CATa and CATb, and also created developers, CATx and CATy, with all fields populated. CATa is already used by a context scheme. CATx has the name “Business Process Context”. There is also the context category “Business Search Process” created by the devx developer.

### Test Step:

1. An OAGi developer logs into the system.
2. The developer creates a new context category, say CAT0, specifying only the Name field.
3. Verify that CAT0 exists on the “Context Category” page. (Assertion #1)
4. The developer creates a new context category, say CAT1, specifying the Name field and Description field.
5. The developer opens CAT1 to view its detail. Verify that both the Name and Description are correct. (Assertion #2)
6. The developer tries to create a new context category, say CAT3, specifying only the Description field.
7. Verify that the “Create” button is disabled. (Assertion #3)
8. The developer visits the “Context Category” page.
9. Verify that the developer can see in the list CATa, CATb, CATx, CATy, CAT0 and CAT1 (Assertion #4)
10. Verify that the developer can open a CATa and that it is editable. (Assertion #5)
11. The developer visits the “Context Category” page again.
12. Verify that the developer can open CATx and that it is editable. (Assertion #5)
13. The developer removes all the content in the Description field of CATx and click “Update”.
14. Verify that both the Description content in the “Context Category” page match the input value of the previous change. (Assertion #6)
15. The developer opens a context category CATa.
16. The developer changes both the Name and Description and click “Update”.
17. Verify that both the Name and Description contents in the “Context Category” page and in the “Context Category Detail” page match the new input values. (Assertion #7)
18. The developer opens CATb.
19. The developer removes the content in the Name field and tries to click “Update” button.
20. Verify that the “Update” button is disabled. (Assertion #8)
21. The developer opens CATb.
22. Clicks “Discard”.
23. Verify that CATb does not shown up on the “Context Category” page. (Assertion #9)
24. The developer opens CATy.
25. Clicks “Discard”.
26. Verify that CATy does not shown up on the “Context Category” page. (Assertion #9)
27. The developer opens CATa.
28. Clicks “Discard”.
29. Verify that the system indicates that the context category cannot be discarded and that it is still listed on the “Context Category” page. Also verify that the checkbox located in front of the CATa in the “Context Category” page is disabled.  (Assertion #10)
30. The developer visits the “Context Category” page.
31. Developer enters the search term “usiness” that is partially match some names of the context categories into the Name field.
32. Verify that at least CATx is returned. (Assertion #11)
33. The developer enters the search term “searchDesc” that is partially match some names of the context categories into the Description field.
34. Verify that at least CATa is returned. (Assertion #11)
35. The developer enters the term “business process” to the Name field.
36. Verify that at least the “Business Process Context” and the “Business Search Process” are returned. (Assertion #11)
37. The developer enters the term “”business process”” to the Name field.
38. Verify that the “Business Process Context” is returned but not the “Business Search Process”. (Assertion #11)
39. The developer visits the Context Category page, he selects a Context Category (clicking the corresponding checkbox), goes to the next paginator pages and then returns back.
40. Verify that the checkbox of the selected Context Category is checked. (Assertion #12)