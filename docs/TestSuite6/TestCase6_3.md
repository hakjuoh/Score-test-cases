## Test Case 6.3

> End user authorized access to BIE Expression generation

Pre-condition: N/A



### Test Assertion:

1. The end user can generate an expression of a BIE that he owns in any state. Test for:
	1. When the latest release is selected.
	2. When one of the older releases is selected.
2. The end user cannot generate an expression of a BIE which is in WIP state and owned by another user.
3. The end user can generate an expression of a BIE which is in QA state and owned by another user.
4. The end user can generate an expression of a Production BIE owned by another user.
5. The end user can generate an expression of a single BIE, in XML Schema, in the same package, with no annotation selected.
6. The end user can generate an expression of a single BIE, in XML Schema, in the same package, with all the annotations selected.
7. The end user can generate an expression of a single BIE, in XML Schema, in the same package, with the BIE CCTS Meta Data annotation selected but not the Include CCTS_Definition Tag annotation.
8. The end user can generate an expression of a single BIE, in XML Schema, in the same package, with the BIE OAGi/Score Meta Data annotation selected but not the Include WHO Columns annotation.
9. The end user cannot generate an expression of a single BIE, in XML Schema, with the Include CCTS_Definition Tag annotation selected but not the BIE CCTS Meta Data annotation.
10. The end user cannot generate an expression of a single BIE, in XML Schema, with the Include WHO Columns annotation selected but not the BIE OAGi/Score Meta Data annotation.
11. The end user can generate an expression of a single BIE, in JSON Schema, in the same package, with no annotation selected.
12. The end user can generate an expression of a single BIE, in JSON Schema, in the same package, with the BIE Definition annotation selected.
13. The end user cannot generate an expression of a single BIE, in JSON Schema, in the same package, with any of the BIE CCTS Meta Data, Include CCTS_Definition Tag, BIE GUID, Business Context, BIE OAGi/Score Meta Data, Include WHO Columns, Based CC Meta Data annotations selected.
14. The end user can generate an expression of multiple BIEs, in multiple XML Schemas, saved in the same package, with some annotations selected.
15. The end user can generate an expression of multiple BIEs, in XML Schemas, saved in different packages, with some annotations selected.
16. The end user can generate an expression of multiple BIEs, in JSON Schemas, saved in the same package, with the BIE Definition selected.
17. The end user can generate an expression of multiple BIEs, in JSON Schemas, saved in different packages, with the BIE Definition selected.
18. The end user can generate an expression of a single BIE, in JSON Schema, having selected a Meta Header (Include Meta Header). Also, verify that the “metaheader” property is an object and not an array.
	1. The end user can generate an expression of a single BIE, in JSON Schema, having selected a Meta Header and the option “Make as an array”. Verify that the “metaheader” property is an object and not an array.
	2. The end user can generate an expression of a single BIE, in JSON Schema, having selected a Meta Header and a Pagination Response. Verify that the “metaheader” property is an object and not an array.
	3. The end user can generate an expression of a single BIE, in JSON Schema, having selected a Meta Header, Pagination Response and the option “Make as an array”. Verify that the “metaheader” property is an object and not an array.
19. The end user can generate an expression of multiple BIEs, in JSON Schemas, saved in different packages, while selecting a Meta Header (Include Meta Header).
20. The search function is at least working.
21. The number of BIEs in the Express BIE page should be the same with the number of BIEs displaying in the index box located at the bottom right of the page.
22. The end user can generate an expression of a single BIE with multiple business contexts assigned, in XML Schema, in the same package, with the Business Context annotation selected.
23. The end user can generate Open API 3.0 in YAML with GET Operation Template that includes Make Array, Meta Header, and Pagination Response options and POST Operation Template that includes Meta Header and Make Array options. The end user must be able to select Meta Header BIE and Pagination Response BIE owned by another end user only in QA or Production state.
24. The end user can generate Open API 3.0 in JSON with GET Operation Template that includes Meta Header, Pagination Response, and Make Array option and POST Operation Template that includes Meta Header and Make Array option. The end user must be able to select Meta Header BIE and Pagination Response BIE owned by a developer user only in QA or Production state.
25. The end user can generate an expression of a single BIE, in JSON Schema, having selected a Pagination Response (Include Pagination Response). Also, verify that the “paginationResponse” property is an object and not an array.
	1. The end user can generate an expression of a single BIE, in JSON Schema, having selected a Pagination Response and the option “Make as an array”. Verify that the “paginationResponse” property is an object and not an array.
26. The end user cannot generate an expression of multiple BIEs, in JSON Schemas, saved in the same package if he has selected a Meta Header or a Pagination Response (the option “Put all schemas in the same file” is disabled).
27. The end user can express a reusing BIE when the same reused BIE is reused in multiple places. Check both XML and JSON generation.
28. The end user can generate an expression of a single BIE, in Open API 3.0 in YAML with Code Generation Friendly, in single file.
29. The end user can generate an expression of a multiple BIEs, in Open API 3.0 in YAML with Code Generation Friendly saved in different packages.
30. The end user can generate an expression of a single BIE, in Open API 3.0 in JSON with Code Generation Friendly, in single file.
31. The end user can generate an expression of a multiple BIEs, in Open API 3.0 in JSON with Code Generation Friendly saved in different packages.
32. The end user can generate an expression of a single BIE, in Open API 3.0 in YAML with Code Generation Friendly, GET Operation Template and Make Array option, in single file.
33. The end user can generate an expression of multiple BIEs, in Open API 3.0 in YAML with Code Generation Friendly, GET Operation Template and Make Array option, in different packages.
34. The end user can generate an expression of a single BIE, in Open API 3.0 in YAML with Code Generation Friendly, GET Operation Template that includes Meta Header, in single file.
35. The end user can generate an expression of multiple BIEs, in Open API 3.0 in YAML with Code Generation Friendly, GET Operation Template that includes Meta Header, in different packages.
36. The end user can generate an expression of a single BIE, in Open API 3.0 in YAML with Code Generation Friendly, GET Operation Template that includes Meta Header and Pagination Response, in single file.
37. The end user can generate an expression of multiple BIEs, in Open API 3.0 in YAML with Code Generation Friendly, GET Operation Template that includes Meta Header and Pagination Response, in different packages.
38. The end user can generate an expression of a single BIE, in Open API 3.0 in YAML with Code Generation Friendly, POST Operation Template and Make Array option, in single file.
39. The end user can generate an expression of multiple BIEs, in Open API 3.0 in YAML with Code Generation Friendly, POST Operation Template and Make Array option, in different packages.
40. The end user can generate an expression of a single BIE, in Open API 3.0 in YAML with Code Generation Friendly, POST Operation Template that includes Meta Header, in single file.
41. The end user can generate an expression of multiple BIEs, in Open API 3.0 in YAML with Code Generation Friendly, POST Operation Template that includes Meta Header, in different packages.
42. The end user can generate an expression of a single BIE, in Open API 3.0 in YAML with Code Generation Friendly, GET Operation Template that includes Meta Header, Pagination Response, and Make Array option, in single file.
43. The end user can generate an expression of multiple BIEs, in Open API 3.0 in YAML with Code Generation Friendly, GET Operation Template that includes Meta Header, Pagination Response, and Make Array option, in different packages.
44. The end user can generate an expression of a single BIE, in Open API 3.0 in YAML with Code Generation Friendly, GET Operation Template that includes Meta Header, Pagination Response, and Make Array option as well as POST Operation Template that includes Meta Header, Pagination Response, and Make Array option, in single file.
45. The end user can generate an expression of multiple BIEs, in Open API 3.0 in YAML with Code Generation Friendly, GET Operation Template that includes Meta Header, Pagination Response, and Make Array option as well as POST Operation Template that includes Meta Header, Pagination Response, and Make Array option, in different packages.
46. The end user can generate an expression of a single BIE, in Open API 3.0 in JSON with Code Generation Friendly, GET Operation Template that includes Meta Header, Pagination Response, and Make Array option as well as POST Operation Template that includes Meta Header, Pagination Response, and Make Array option, in single file.
47. The end user can generate an expression of multiple BIEs, in Open API 3.0 in JSON with Code Generation Friendly, GET Operation Template that includes Meta Header, Pagination Response, and Make Array option as well as POST Operation Template that includes Meta Header, Pagination Response, and Make Array option, in different packages.

### Test Step Pre-condition:

1. There are some BIEs created by users, namely BIEa, BIEb, BIEc, which are in Editing, Candidate and Published correspondingly. Additionally, there are some BIEs created by a developer, namely BIE0, BIE1, BIE2, which are in Editing, Candidate and Published correspondingly. The name of the BIE1 is “Acknowledge Receive Item”. Finally, there is a BIE, BIE3, created by a developer with multiple business contexts assigned.

### Test Step:

1. An end user logs into the system.
2. He goes to the Generate Expression page.
3. Verify that he cannot view the BIE0 and so he cannot generate an expression of it, while he can view BIEa, BIEb, BIEc, BIE1 and BIE2 and so he can generate an expression of them. (Assertion #1 #2 #3 #4)
4. The user generates an expression from BIEb, in XML Schema, selecting no annotation and that the scheme will be saved in the same package.
5. Verify that the Schema is successfully generated and saved in the same package. (Assertion #5)
6. The user generates an expression from BIEc, in XML Schema, selecting all the annotations and that the scheme will be saved in the same package.
7. Verify that the Schema is successfully generated and saved in the same package. (Assertion #6)
8. The user generates an expression from BIE1, in XML Schema, selecting the BIE CCTS Meta Data annotation but not the Include CCTS_Definition Tag annotation and that the scheme will be saved in the same package.
9. Verify that the Schema is successfully generated and saved in the same package. (Assertion #7)
10. The user generates an expression from BIE2, in XML Schema, selecting the BIE OAGi/Score Meta Data annotation but not the Include WHO Columns annotation and that the schema will be saved in the same package.
11. Verify that the Schema is successfully generated and saved in the same package. (Assertion #8)
12. The user generates an expression from BIE2, in XML Schema, selecting the Include CCTS_Definition Tag annotation but not the BIE CCTS Meta Data annotation.
13. Verify that the Include CCTS_Definition Tag annotation cannot be selected without selecting the BIE CCTS Meta Data annotation first. (Assertion #9)
14. The user generates an expression from BIE2, in XML Schema, selecting the Include WHO Columns annotation but not the BIE OAGi/Score Meta Data annotation.
15. Verify that the Include WHO Columns annotation cannot be selected without selecting the BIE OAGi/Score Meta Data annotation first. (Assertion #10)
16. The user generates an expression from BIEb, in JSON Schema, selecting that the schema will be saved in the same package and without selecting any annotation.
17. Verify that the Schema is successfully generated. (Assertion #11)
18. The user generates an expression from BIE1, in JSON Schema, selecting the BIE Definition annotation and that the schema will be saved in the same package.
19. Verify that the Schema is successfully generated and saved in the same package. (Assertion #12)
20. The user generates an expression from BIE2, in JSON Schema, selecting the BIE CCTS Meta Data, Include CCTS_Definition Tag, BIE GUID, Business Context, BIE OAGi/Score Meta Data, Include WHO Columns, Based CC Meta Data annotations.
21. Verify that the aforementioned annotations cannot be selected. (Assertion #13)
22. The user generates an expression from BIEb and BIE1, in XML Schemas, selecting some annotations and that the XML Schemas will be saved in the same package.
23. Verify that the Schemas are successfully generated and saved in the same package. (Assertion #14)
24. The user generates an expression from BIEb and BIE1, in XML Schemas, selecting some annotations and that the XML Schemas will be saved in different packages.
25. Verify that the Schemas are successfully generated and saved in different packages. (Assertion #15)
26. The user generates an expression from BIEb and BIE1, in JSON Schemas, selecting the BIE definition annotation and that the JSON Schemas will be saved in the same package.
27. Verify that the Schemas are successfully generated and saved in the same package. (Assertion #16)
28. The user generates an expression from BIEb and BIE1, in JSON Schemas, selecting the BIE Definition annotation and that the JSON Schemas will be saved in different packages.
29. Verify that the Schemas are successfully generated and saved in different packages. (Assertion #17)
30. The user generates an expression from BIE1, in JSON Schema, selecting the BIE Definition annotation and that the schema will be saved in the same package. Also, he selects Include Meta Header and selects a corresponding BIE.
31. Verify that the Schema is successfully generated (Assertion #18)
32. The user generates an expression from BIEb and BIE1, in JSON Schemas, selecting the BIE Definition annotation and that the schemas will be saved in different packages. Also, he selects Include Meta Header and selects a corresponding BIE.
33. Verify that the Schemas are successfully generated (Assertion #19)
34. The user enters the search term “eceive” in the Property Term search field that partially matches some BIEs’ names.
35. Verify that at least the BIE “Receive Item” is returned. (Assertion #20)
36. The user clears all filters and he chooses user devx at the Owner search filter select.
37. Verify that at least the BIE “Receive Item” is returned. (Assertion #20)
38. The user clears all filters and he chooses devx at the Updater search filter.
39. Verify that at least the BIE “Receive Item” is returned. (Assertion #20)
40. The user clears all filters and he chooses a recent day at the Updated start date search filter.
41. Verify that at least the BIE “Receive Item” is returned. (Assertion #20)
42. The user clears all filters and he chooses the Candidate state at the State search filter.
43. Verify that at least the BIE “Receive Item” is returned. (Assertion #20)
44. The user clears all filters and enters the search term “initBC” in Business Context Search field that matches some BIE’s business contexts.
45. Verify that at least the BIE “Receive Item” is returned. (Assertion #20)
46. The user opens the “Express BIE” page.
47. Verify that the number of BIEs is the same with the number of BIEs displaying in the index box located at the bottom right of the page by visiting each index page. (Assertion #21)
48. The user opens the “Express BIE” page.
49. The user generates an expression from BIE3, in XML Schema, selecting the Business Context annotation.
50. Verify that the Schema is successfully generated. (Assertion #22)