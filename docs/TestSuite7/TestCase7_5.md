## Test Case 7.5

> OAGi Terminology Append an Association Dialog

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
The Den field of the dialog where you append an ASCCP while editing an extension (local or global) should be “DEN (Dictionary Entry Name)”.

#### Test Assertion #2
The Module field filter of the dialog where you append an ASCCP while editing an extension (local or global) should be “Module (Part of schema file path, no extension)”.

#### Test Assertion #3
The Den field of the dialog where you append a BCCP while editing an extension (local or global) should be “DEN (Dictionary Entry Name)”.

#### Test Assertion #4
The Module field filter of the dialog where you append a BCCP while editing an extension (local or global) should be “Module (Part of schema file path, no extension)”.

### Test Step Pre-condition:

1. There is the BIE BIE0 created by the developer account used in asserting this test case.

### Test Step:

1. An OAGi developer logs into the system.
2. The developer opens the BIE0 and extends it locally.
3. He opens the BIE0’s local extension.
4. He appends an ASCCP.
5. Verify that the dialog where you select an ASCCP to append has the search field “DEN (Directory Entry Name)”. (Assertion [#1](#test-assertion-1))
6. Verify that the dialog where you select an ASCCP to append has the search field “Module (Part of schema file path, no extension)”. (Assertion [#2](#test-assertion-2))
7. He closes the dialog and tries to append a BCCP.
8. Verify that the dialog where you select an BCCP to append has the search field “DEN (Directory Entry Name)”. (Assertion [#3](#test-assertion-3))
9. Verify that the dialog where you select an BCCP to append has the search field “Module (Part of schema file path, no extension)”. (Assertion [#4](#test-assertion-4))