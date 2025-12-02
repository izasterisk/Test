# UNIT TEST - Register

| Function Code | AUTH-002 | Function Name | | CreateUserAsync |
|---------------|----------|---------------|---|-----------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 20 | **Lack of test cases** | | |
| **Test requirement** | Verify user registration with email and password | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 7 | 1 | 4 | 2 | 7 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O |
| | **dto** | | | | | | | | | |
| | | Valid UserCreateDTO | | O | | | | | | |
| | | null | | | O | | | | | |
| | **email** | | | | | | | | | |
| | | newuser@gmail.com | | O | | | | | | |
| | | existed@gmail.com | | | | O | | | | |
| | | invalidformat | | | | | O | | | |
| | | null | | | | | | O | | |
| | **password** | | | | | | | | | |
| | | ValidP@ss123 | | O | | | | | | |
| | | 123 | | | | | | | O | |
| | | null | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | |
| | | T | | O | | | | | | |
| | | F | | | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | |
| | | ArgumentNullException | | | O | | | | | |
| | | Exception | | | | O | O | O | O | O |
| **Log message** | | | | | | | | | | |
| | | "User created successfully" | | O | | | | | | |
| | | "dto rỗng." | | | O | | | | | |
| | | "Email already exists" | | | | O | | | | |
| | | "Invalid email format" | | | | | O | | | |
| | | "Email is required" | | | | | | O | | |
| | | "Password too short" | | | | | | | O | |
| | | "Password is required" | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | B | A |
| | | Passed/Failed | | | | | | | | |
| | | Executed Date | | | | | | | | |
| | | Defect ID | | | | | | | | |
