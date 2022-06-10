## Test Case 2.2

> OAGIS developer can manage end user accounts

Pre-condition: N/A



### Test Assertion:

1. An OAGIS developer can successfully create an end user account with all valid information.
2. An OAGIS developer cannot create an end user account with a duplicate login ID.
3. An OAGIS developer cannot create an end user account that does not meet password rules.
4. An OAGIS developer cannot update the log in ID of an end user account with a new unique log in ID.
5. An OAGIS developer can update the password of an end user account with a new password that meet password rules.
6. An OAGIS developer cannot update the password of an end user account with a new password that does not meet password rules.
7. An OAGIS developer can disable an end user account. Disable account cannot be used for logging in to the application.
8. An OAGIS developer can enable a disabled end user account. Enable account can be used for logging in to the application.
9. An OAGIS developer can approve or reject a single sign on request by an end user when the application is set up with SSO.

### Test Step Pre-condition:

1. The end user accounts to be created do not exist.

### Test Step:

1. Logs into the Score with the built-in developer account.
2. The developer goes to the Accounts page.
3. The developer creates a new (say eusername1) end user account with all valid information.
4. The built-in developer user logs out.
5. Logs into the Score with the new end user account.
6. Verify that the log in was successful (e.g., by verifying that the label of the top-right menu matches with the username). (Assertion #1)
7. The end user logs out.
8. The user logs into the Score with the built-in developer account.
9. The developer user tries to create a new end user account with all valid information, however, with the same username as the previous end user account.
10. Verify that the system reports an error. (Assertion #2)
11. The developer user tries to create a new end user account with all valid information except the password. The password does not meet the password rule.
12. Verify that an error box is displayed and that the Create button is disabled. Note that this and the previous steps may be repeated for various password rules. (Assertion #3)
13. The OAGIS developer tries to update the end user account username of eusername1 to, say, eusername2 that is unique to the system.
14. Verify that the login ID field is disabled. (Assertion #4)
15. The OAGIS developer changes the password of the end user account to a new valid password.
16. The OAGIS developer log out.
17. Verify that the end user can log in with the new username and password. (Assertion #5)
18. The OAGIS developer updates the password of the end user account to a password that does not meet password rules.
19. Verify that an error box is displayed, the Update button is disabled and that the eusername1 can still login using the previous valid password. (Assertion #6)