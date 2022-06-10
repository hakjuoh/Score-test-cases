## Test Case 7.6

> OAGi Terminology Core Component

Pre-condition: N/A



### Test Assertion:

1. The name of the Core Component page should be “Core Components (Model Library)”.
2. The Den field filter of the Core Component page should be “DEN (Dictionary Entry Name)”.
3. The Module field filter of the Core Component page should be “Module (Part of schema file path, no extension)”.
4. The title of the left pane where the tree of an ACC is displayed should be “ACC (Component Type or Group Definition)”.
5. The Object Class Term of an ACC should be “Object Class Term (Space Separated Name)”.
6. The Den of an ACC should be “DEN (Dictionary Entry Name)”.
7. The title of the left pane where the tree of an ASCCP is displayed should be “ASCCP (Component or Group Definition)”.
8. The title of the right pane where the details of an ASCCP are displayed should be “ASCCP (Associated Component) Detail”.
9. The Property Term of an ASCCP should be “Property Term (Component Name)”.
10. The Den of an ASCCP should be “DEN (Dictionary Entry Name)”.
11. The title of the right pane where the details of a BCCP are displayed should be “BCCP (Associated Field) Detail”.
12. The Property Term of a BCCP should be “Property Term (Field Name)”.
13. The Den of a BCCP should be “DEN (Dictionary Entry Name)”.
14. The title of the right pane where the details of an ASCC are displayed should be “ASCC (Component Association) Detail”. (It cannot be checked yet)
15. The Max Cardinality field of an ASCC should be “Cardinality Max (-1 for unbounded)”.
16. The Den of an ASCC should be “DEN (Dictionary Entry Name)”.
17. The title of the right pane where the details of a BCC are displayed should be “BCC (Field Association) Detail”
18. The Max Cardinality field of a BCC should be “Cardinality Max (-1 for unbounded)”.
19. The Den of n BCC should be “DEN (Dictionary Entry Name)”.
20. The title of the right pane where the details of a supplementary component are displayed should be “Supplementary Component (Field Metadata)”. (It cannot be checked yet)
21. The Max Cardinality field of a supplementary component should be “Cardinality Max (-1 for unbounded)”.
22. The Den of a supplementary component should be “DEN (Dictionary Entry Name)”.
23. The Den of a Data type component should be “DEN (Dictionary Entry Name)”.

### Test Step Pre-condition:

1. There is the BIE BIEa created by the developer account used in asserting this test case. The BIEa is locally and globally extended. These extensions contain an ASCCP and a BCCP association.
2. There is the ACC0, ASCCP0, BCCP0, ASCC0

### Test Step:

1. An OAGi developer logon into the system.
2. He visits the Core Component page.
3. Verify that the title of the page is “Core Components (Model Library)”. (Assertion #1)
4. Verify that there is the search field “DEN (Directory Entry Name)”. (Assertion #2)
5. Verify that there is the search field “Module (Part of schema file path, no extension)”. (Assertion #3)
6. He opens the ACC0
7. Verify that the left panel where the tree of the ACC0 is displayed has the title “ACC (Component Type or Group Definition)”. (Assertion #4)
8. Verify that Object Class Term of the ACC0 is “Object Class Term (Space Separated Name)”. (Assertion #5)
9. Verify that there is the “DEN (Dictionary Entry Name)” input field. (Assertion #6)
10. The developer visits the Core Component page.
11. He opens the ASCCP0
12. Verify that the left panel where the tree of the ASCCP0 is displayed has the title “ASCCP (Associated Component) Detail”. (Assertion #7)
13. Verify that the title of the right panel where the details of an ASCCP are displayed is “ASCCP (Associated Component) Detail”. (Assertion #8)
14. Verify that there is the field “Property Term (Component Name)”. (Assertion #9)
15. Verify that there is the “DEN (Dictionary Entry Name)” input field. (Assertion #10)
16. The developer opens the BIEa’s local extension and clicks to view an ASCCP.
17. Verify that Object Class Term is “ASCCP (Associated Component) Detail”. (Assertion #8)
18. Verify that there is the “DEN (Dictionary Entry Name)” input field. (Assertion #10)
19. Verify that there is the field “Property Term (Component Name)”. (Assertion #9)
20. The developer opens the BIEa’s global extension and clicks to view an ASCCP
21. Verify that Object Class Term is “ASCCP (Associated Component) Detail (Assertion #8)
22. Verify that there is the “DEN (Dictionary Entry Name)” input field. (Assertion #10)
23. Verify that there is the field “Property Term (Component Name)”. (Assertion #9)
24. The developer visits the Core Component page.
25. He opens the BCCP0
26. Verify that the object class term is “BCCP (Associated Field) Detail”. (Assertion #11)
27. Verify that there is the field “Property Term (Component Name)”. (Assertion #12)
28. Verify that there is the “DEN (Dictionary Entry Name)” input field. (Assertion #13)
29. The developer opens the BIEa’s local extension and clicks to view an BCCP.
30. Verify that the class term is “BCCP (Associated Field) Detail”. (Assertion #11)
31. Verify that there is the field “Property Term (Component Name)”. (Assertion #12)
32. Verify that there is the “DEN (Dictionary Entry Name)” input field. (Assertion #13)
33. The developer opens the BIEa’s global extension and clicks to view an BCCP.
34. Verify that the class term is “BCCP (Associated Field) Detail”. (Assertion #11)
35. Verify that there is the field “Property Term (Component Name)”. (Assertion #12)
36. Verify that there is the “DEN (Dictionary Entry Name)” input field. (Assertion #13)
37. The developer opens the BIEa’s local extension and clicks to view an ASCC.
38. Verify that the class term is “ASCC (Component Association) Detail”. (Assertion #14)
39. Verify that the name of the Max Cardinality field is “Cardinality Max (-1 for unbounded)”. (Assertion #15)
40. Verify that there is the field “DEN (Dictionary Entry Name)”. (Assertion #16)
41. The developer opens the BIEa’s global extension and clicks to view an ASCC.
42. Verify that the class term is “ASCC (Component Association) Detail”. (Assertion #14)
43. Verify that the name of the Max Cardinality field is “Cardinality Max (-1 for unbounded)”. (Assertion #15)
44. Verify that there is the field “DEN (Dictionary Entry Name)”. (Assertion #16)
45. The developer opens the BIEa’s local extension and clicks to view a BCC.
46. Verify that the class term is “BCC (Field Association) Detail”. (Assertion #17)
47. Verify that the name of the Max Cardinality field is “Cardinality Max (-1 for unbounded)”. (Assertion #18)
48. Verify that there is the field “DEN (Dictionary Entry Name)”. (Assertion #19)
49. The developer opens the BIEa’s global extension and clicks to view a BCC.
50. Verify that the class term is “BCC (Field Association) Detail”. (Assertion #17)
51. Verify that the name of the Max Cardinality field is “Cardinality Max (-1 for unbounded)”. (Assertion #18)
52. Verify that there is the field “DEN (Dictionary Entry Name)”. (Assertion #19)
53. The developer opens the BIEa’s local extension and clicks to view a supplementary component.
54. Verify that the name of the Max Cardinality field is “Cardinality Max (-1 for unbounded)”. (Assertion #21)
55. Verify that there is the field “DEN (Dictionary Entry Name)”. (Assertion #22)
56. The developer opens the BIEa’s global extension and clicks to view a supplementary component.
57. Verify that the name of the Max Cardinality field is “Cardinality Max (-1 for unbounded)”. (Assertion #21)
58. Verify that there is the field “DEN (Dictionary Entry Name)”. (Assertion #22)
59. The developer opens the BIEa’s local extension and clicks to view a Data Type component.
60. Verify that there is the field “DEN (Dictionary Entry Name)”. (Assertion #23)
61. The developer opens the BIEa’s global extension and clicks to view a Data Type component
62. Verify that there is the field “DEN (Dictionary Entry Name)”. (Assertion #23)