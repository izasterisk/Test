# UNIT TEST - ChangePassword

| Function Code | AUTH-003 | Function Name | | ChangePassword |
|---------------|----------|---------------|---|----------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 15 | **Lack of test cases** | | |
| **Test requirement** | Verify password change with old and new password | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 8 | 1 | 5 | 2 | 8 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O |
| | **email** | | | | | | | | | | |
| | | valid@gmail.com | | O | | | | | | | |
| | | notexist@gmail.com | | | O | | | | | | |
| | | null | | | | O | | | | | |
| | **oldPassword** | | | | | | | | | | |
| | | CorrectPassword | | O | | | | | | | |
| | | WrongPassword | | | | | O | | | | |
| | | null | | | | | | O | | | |
| | **newPassword** | | | | | | | | | | |
| | | NewValidP@ss123 | | O | | | | | | | |
| | | 123 | | | | | | | O | | |
| | | null | | | | | | | | O | |
| | **user status** | | | | | | | | | | |
| | | Active, IsVerified=true | | O | | | | | | | |
| | | Inactive | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | |
| | | T | | O | | | | | | | |
| | | F | | | O | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | | |
| | | InvalidOperationException | | | O | O | O | O | O | O | O |
| **Log message** | | | | | | | | | | | |
| | | "Password changed successfully" | | O | | | | | | | |
| | | "User not found" | | | O | | | | | | |
| | | "Email is required" | | | | O | | | | | |
| | | "Old password incorrect" | | | | | O | | | | |
| | | "Old password is required" | | | | | | O | | | |
| | | "New password too short" | | | | | | | O | | |
| | | "New password is required" | | | | | | | | O | |
| | | "User is inactive" | | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | B | A | A |
| | | Passed/Failed | | | | | | | | | |
| | | Executed Date | | | | | | | | | |
| | | Defect ID | | | | | | | | | |
