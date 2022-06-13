## Test Case 6.1

> End user's authorized management of context schemes

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
The end user can see, in the context scheme list, all context schemes created by any user.

#### Test Assertion #2
The end user can edit a context scheme created by any user.

#### Test Assertion #3
The end user can add to a context scheme code list values from Published Code Lists. (The code values are simply copied into the context scheme). The end user shall be notified that existing values will be removed. Test for:

	1. A developer code list in the latest release.
	2. A developer code list in an older release.

#### Test Assertion #4
The end user can add to a context scheme code list values from Production Code Lists. Test for

	1. An end user code list in the latest release that is derived from another developer code list
	2. An end user code list in a non latest release that is derived from another developer code list

#### Test Assertion #5
The end user can select a Context Scheme from the Context Scheme List page, navigate through different paginator pages while the forenamed Context Scheme remains checked.

### Test Step Pre-condition:



### Test Step: