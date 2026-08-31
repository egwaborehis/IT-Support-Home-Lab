# Test 05 — User Accounts & Permissions

## Overview

This test was created to practise basic user account and permission management skills that are relevant to an IT support or help desk environment.

The main purpose was to understand the difference between an Administrator account and a Standard User account, and to see how Windows protects important system locations from normal users.

Rather than only reading about permissions, I created a temporary Standard User account and performed a controlled test using the `C:\Program Files` directory.

The investigation covered:

- Windows user account types
- Administrator accounts
- Standard User accounts
- Local user accounts
- File and folder permissions
- Protected Windows locations
- User Account Control (UAC)
- Administrator elevation
- Comparing Standard User and Administrator access
- Safe testing and cleanup
- Evidence collection and documentation

---

# 1. Checking the Existing Account

Before creating the test account, I checked the account type of my normal Windows account.

The account was confirmed to have:

```text
Administrator
```

Administrator accounts have elevated permissions that allow them to perform certain system-level tasks that Standard Users cannot normally perform.

This was important because I wanted to compare the behaviour of an Administrator account with a Standard User account.

---

# 2. Creating a Test Standard User

To safely perform the permissions test, I created a separate local Windows account named:

```text
SupportLabUser
```

The account was created as a:

```text
Standard user
```

I deliberately kept my normal account unchanged and did not remove administrator access from it.

This allowed the test to be performed without risking access to my main Windows account.

### Evidence

[View the Standard User account evidence](standard-user-account.png)

The screenshot shows `SupportLabUser` as a local account with the account type set to **Standard user**.

---

# 3. Understanding Administrator vs Standard User

Windows provides different account types with different levels of access.

## Administrator

An Administrator account has elevated permissions that allow the user to perform system-level operations.

Examples can include:

- Installing software
- Changing certain system settings
- Managing other user accounts
- Modifying protected system locations
- Approving administrator-level operations

Administrator access does not mean that every action happens without confirmation.

Windows can still use **User Account Control (UAC)** to ask the user to confirm an operation that requires elevation.

---

## Standard User

A Standard User has more restricted permissions.

The account can still perform normal everyday activities such as:

- Using applications
- Creating personal files
- Browsing the internet
- Working with files in locations where the user has permission

However, Windows restricts Standard Users from making certain changes to protected system areas.

This helps prevent accidental or unauthorised changes to important parts of the operating system.

---

# 4. Testing Standard User Permissions

After creating `SupportLabUser`, I signed into the account.

I then opened:

```text
C:\Program Files
```

`Program Files` is a protected Windows location where applications are commonly installed.

I attempted to create a temporary folder called:

```text
ITSupportLabTest
```

The purpose was not to actually modify the system, but to see how Windows handled the permission request.

---

# 5. Standard User Permission Result

Windows displayed:

```text
Destination Folder Access Denied
```

The message also stated:

```text
You need to confirm this operation.
```

The operation displayed a **Continue** button with the administrator shield icon.

### Evidence

[View the Standard User permission restriction](standard-user-permission-denied.png)

The result demonstrated that the Standard User could not simply make the protected change without administrator-level approval.

I did not enter administrator credentials or force the operation to continue.

Instead, I cancelled the operation because the permission restriction itself was the evidence required for the test.

---

# 6. Why Windows Protects Program Files

`C:\Program Files` is an important Windows location because it commonly contains installed applications and their supporting files.

Allowing every normal user to freely modify this directory could create security and reliability problems.

For example, unrestricted access could allow a user or malicious software to:

- Modify application files
- Replace program components
- Delete important files
- Install unauthorised software components
- Change files used by other users

Restricting access helps protect the operating system and installed applications.

This is one reason why understanding permissions is important in IT support.

---

# 7. Returning to the Administrator Account

After testing the Standard User account, I signed out and returned to my normal Windows Administrator account.

I then repeated the same basic operation in:

```text
C:\Program Files
```

This was important because using the same location allowed me to make a more meaningful comparison between the two account types.

---

# 8. Administrator Permission Test

While using my Administrator account, Windows again displayed a confirmation message before allowing the protected operation.

The message stated:

```text
Destination Folder Access Denied
```

and:

```text
You need to confirm this operation.
```

The **Continue** button displayed the administrator shield.

This demonstrates that being an Administrator does not necessarily mean Windows automatically performs every protected action.

Instead, Windows can use User Account Control to require the Administrator to approve an elevated operation.

---

# 9. Successful Administrator Operation

After confirming the operation, Windows allowed the temporary folder to be created inside:

```text
C:\Program Files
```

The folder was named:

```text
ITSupportLabAdminTest
```

### Evidence

[View the successful Administrator operation](administrator-permission-success.png)

The screenshot shows the temporary folder successfully created inside `C:\Program Files`.

This provided the second half of the permissions comparison.

---

# 10. Comparing the Results

The two accounts produced different results when attempting to perform the same type of protected operation.

| Account | Location | Result |
|---|---|---|
| Standard User | `C:\Program Files` | Restricted / required administrator approval |
| Administrator | `C:\Program Files` | Operation could be approved and completed |

This demonstrates the practical difference between the two account types.

A simplified representation is:

```text
Standard User
      ↓
Attempts protected operation
      ↓
Windows restricts operation
      ↓
Administrator approval required


Administrator
      ↓
Attempts protected operation
      ↓
Windows requests elevation/confirmation
      ↓
Administrator approves
      ↓
Operation succeeds
```

---

# 11. Understanding User Account Control (UAC)

The administrator shield displayed on the **Continue** button is associated with User Account Control.

UAC is a Windows security feature that helps prevent applications or users from silently making changes that require elevated permissions.

This means that even when logged into an Administrator account, Windows can still ask for confirmation before allowing a protected operation.

This is useful because it adds another layer between normal computer use and potentially important system changes.

---

# 12. Why This Matters in IT Support

Understanding account permissions is useful when troubleshooting problems reported by users.

For example, a user might say:

> "I can't install this application."

A technician should not immediately assume that the application is broken.

The issue could be related to the user's account permissions.

Another example could be:

> "I can't modify this folder."

The technician could investigate:

- Which account the user is using
- Whether the account is a Standard User or Administrator
- Where the folder is located
- Whether the folder is protected
- Whether administrator approval is required
- Whether the user should actually have access to that location

This helps the technician distinguish between a software problem and a permissions issue.

---

# 13. Principle of Least Privilege

This exercise also introduced the idea of **least privilege**.

The principle of least privilege means that a user or system should have only the permissions required to perform their intended tasks.

For example, an ordinary user who only needs to browse the internet, use applications and work with personal documents does not necessarily need unrestricted administrator access.

Using Standard User accounts where appropriate can reduce the potential impact of accidental or malicious changes.

In an IT support environment, permissions should therefore be considered carefully rather than automatically giving every user administrator access.

---

# 14. Safe Testing and Cleanup

The test used a separate temporary account so that my normal Administrator account did not need to be changed.

The test folder created during the Administrator permissions test was also temporary.

After the evidence was captured, I removed:

```text
ITSupportLabAdminTest
```

from `C:\Program Files`.

This left the computer in the same general state as before the test.

The temporary Standard User account can also be removed when it is no longer required for the lab.

---

# 15. Evidence Summary

The test produced three main pieces of evidence.

### Evidence 1 — Standard User Account

[View Standard User account evidence](standard-user-account.png)

This shows that `SupportLabUser` was configured as a Standard User.

### Evidence 2 — Standard User Permission Restriction

[View Standard User permission evidence](standard-user-permission-denied.png)

This shows Windows restricting the protected operation when using the Standard User account.

### Evidence 3 — Administrator Permission Success

[View Administrator permission evidence](administrator-permission-success.png)

This shows the temporary folder successfully being created after the Administrator account approved the protected operation.

Together, these screenshots demonstrate the difference between the two account types.

---

# 16. Troubleshooting Scenario

Imagine that a user contacts an IT help desk and says:

> "Windows won't let me install this software."

A basic investigation could be:

```text
User reports permission problem
          ↓
Identify the user's account
          ↓
Check whether it is Standard or Administrator
          ↓
Identify what operation is being attempted
          ↓
Check whether the location/action requires elevation
          ↓
Determine whether administrator approval is appropriate
          ↓
Apply the correct support procedure
```

The technician should not simply give the user administrator access without considering why it is required.

The correct solution could instead involve:

- Providing approved software through the organisation's normal deployment process
- Having an authorised administrator perform the installation
- Checking whether the software is approved
- Checking the user's permissions
- Investigating whether the application has another installation method

This demonstrates why permissions are part of both troubleshooting and security.

---

# 17. What I Learned

This test gave me practical experience with Windows user accounts and permissions.

I learned that:

- Administrator and Standard User accounts have different levels of access.
- Standard Users can perform normal everyday tasks but are restricted from certain protected operations.
- `C:\Program Files` is a protected system location.
- Windows can use User Account Control when an operation requires elevation.
- Administrator accounts can approve certain elevated operations.
- Being an Administrator does not mean every protected operation happens automatically.
- A permissions problem can sometimes look like a software problem.
- A technician should investigate the user's account and the requested operation before changing permissions.
- The principle of least privilege is important when deciding what access a user should have.

---

# 18. Conclusion

The user account and permissions investigation was completed successfully.

I created a separate Standard User account and compared its behaviour with my normal Administrator account.

The Standard User was restricted when attempting to create a folder inside the protected `C:\Program Files` directory.

The Administrator account was able to approve the elevated operation, allowing the temporary folder to be created.

This demonstrated the practical difference between Standard User permissions and Administrator permissions, as well as the role of User Account Control.

The test also showed how permissions can be relevant when troubleshooting real IT support problems.

Rather than immediately changing a user's permissions, a technician should first understand what the user is trying to do, what permissions are required, and whether elevated access is appropriate.

This provides a useful foundation for further IT support work involving user accounts, permissions, software installation and Windows administration.
