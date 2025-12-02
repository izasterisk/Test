# UNIT TEST - Login

| Function Code | AUTH-001 | Function Name | | LoginAsync |
|---------------|----------|---------------|---|------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 40 | **Lack of test cases** | | |
| **Test requirement** | Verify user login with email and password | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 8 | 1 | 5 | 2 | 8 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O |
| | **email** | | | | | | | | | | |
| | | test@gmail.com | | O | | | | | | | |
| | | customer | | | O | | | | | | |
| | | [Existed] customer@gmail.com | | | | | | | | O | |
| | | null | | | | | | | | | O |
| | **password** | | | | | | | | | | |
| | | test | | | | O | | | | | |
| | | Test@1234 | | O | | | | | | | |
| | | WrongPassword | | | | | | | O | | |
| | | null | | | | | O | | | | |
| | **user status** | | | | | | | | | | |
| | | Active, IsVerified=true | | O | | | | | | | |
| | | Inactive | | | | | | O | | | |
| | | IsVerified=false | | | | | | | | O | |
| **Confirm** | **Return** | | | | | | | | | | |
| | | T | | O | | | | | | | |
| | | F | | | O | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | | |
| | | KeyNotFoundException | | | | | | | | | O |
| | | InvalidOperationException | | | O | O | O | O | O | O | |
| **Log message** | | | | | | | | | | | |
| | | "Email is duplicated" | | | | | | | | | |
| | | "Email is required" | | | | | | | | | O |
| | | "Invalid email format" | | | O | | | | | | |
| | | "Password must be at least 6 characters" | | | | O | | | | | |
| | | "Wrong password" | | | | | | | O | | |
| | | "User is not verified" | | | | | | | | O | |
| | | "User is inactive" | | | | | | O | | | |
| | | "Login successfully" | | O | | | | | | | |
| Type(N : Normal, A : Abnormal, B : Boundary) | | | | N | A | B | A | A | A | A | A |
| | | Passed/Failed | | | | | | | | | |
| | | Executed Date | | | | | | | | | |
| | | Defect ID | | | | | | | | | |