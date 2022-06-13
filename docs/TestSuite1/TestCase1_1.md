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