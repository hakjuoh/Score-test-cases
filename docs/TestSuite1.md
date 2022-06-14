# Test Suite 1


## Test Case 1.1

> Built-in OAGIS developer account exists

Pre-condition: N/A


### Test Assertion:

#### Test Assertion #1
Built-in OAGIS developer account exists.

#### Test Assertion #2
Built-in OAGIS developer can successfully login with the valid password.

#### Test Assertion #3
Built-in OAGIS developer can log out.

#### Test Assertion #4
Built-in OAGIS developer account cannot login with an invalid password.

### Test Step Pre-condition:

1. There is no existing user session in the browser.

### Test Step:

1. A user opens the Score homepage.
2. The user logs in with the username "oagis" and valid password, namely "oagis".
3. Verify that the user successfully logged in and that it has the OAGIS developer role. (Assertion [#1](#test-assertion-1), [#2](#test-assertion-2))
4. The user logs out. (Assertion [#3](#test-assertion-3))
5. The user logs in with the username "oagis" and a random invalid password.
6. Verify that the user got notified with an invalid log in. (Assertion [#4](#test-assertion-4))

## Test Case 1.2

> OAGIS developer's authorized functionalities

Pre-condition: N/A
An OAGIS developer can access functionalities (menus) in the test assertion.


### Test Assertion:

#### Test Assertion #1
Create BIE

#### Test Assertion #2
BIE List

#### Test Assertion #3
Copy BIE

#### Test Assertion #4
Generate Expression

#### Test Assertion #5
Context Category

#### Test Assertion #6
Context Scheme

#### Test Assertion #7
Business Context

#### Test Assertion #8
Core Component

#### Test Assertion #9
View Code List (check both locations, i.e., via BIE menu and via Core Component menu)

#### Test Assertion #10
Create Code List w/o base

#### Test Assertion #11
View/Edit Module Set

#### Test Assertion #12
View/Edit Module Set Release

#### Test Assertion #13
View/Edit Release

#### Test Assertion #14
View/Edit Namespace

#### Test Assertion #15
Select a different UI terminology

#### Test Assertion #16
Manage Account

#### Test Assertion #17
Change Password

#### Test Assertion #18
Sign out

#### Test Assertion #19
Uplift BIE

#### Test Assertion #20
Agency ID list

### Test Step Pre-condition:

1. There is no existing user session in the browser.

### Test Step:

1. The user opens the system home page to log in.
2. The user logs in with an OAGIS developer account, preferably not the built-in account.
3. Verify that the menu items identified in the test assertions are accessible to the user. (Assertion [#1](#test-assertion-1) - [#20](#test-assertion-20))