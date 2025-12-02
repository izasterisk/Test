# UNIT TEST - CreateRequest

| Function Code | REQ-001 | Function Name | | CreateRequestAsync |
|---------------|---------|---------------|---|-------------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 30 | **Lack of test cases** | | |
| **Test requirement** | Verify request creation with message and images | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 7 | 1 | 4 | 2 | 7 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O |
| | **userId** | | | | | | | | | |
| | | Valid verified user | | O | | | | | | |
| | | Non-existent user | | | O | | | | | |
| | | Unverified user | | | | O | | | | |
| | | Inactive user | | | | | O | | | |
| | **dto** | | | | | | | | | |
| | | Valid RequestCreateDTO | | O | | | | | | |
| | | null | | | | | | O | | |
| | **requestType** | | | | | | | | | |
| | | Valid request type | | O | | | | | | |
| | | Invalid request type | | | | | | | O | |
| | **description** | | | | | | | | | |
| | | Valid description | | O | | | | | | |
| | | Empty description | | | | | | | | O |
| | **images** | | | | | | | | | |
| | | Valid images list | | O | | | | | | |
| | | Empty images | | O | | | | | | |
| **Confirm** | **Return** | | | | | | | | | |
| | | T | | O | | | | | | |
| | | F | | | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | |
| | | KeyNotFoundException | | | O | | | | | |
| | | InvalidOperationException | | | | O | O | | O | O |
| | | ArgumentNullException | | | | | | O | | |
| **Log message** | | | | | | | | | | |
| | | "Request created successfully" | | O | | | | | | |
| | | "User not found" | | | O | | | | | |
| | | "User not verified" | | | | O | | | | |
| | | "User is inactive" | | | | | O | | | |
| | | "dto is null" | | | | | | O | | |
| | | "Invalid request type" | | | | | | | O | |
| | | "Description required" | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | A | B |
| | | Passed/Failed | | | | | | | | |
| | | Executed Date | | | | | | | | |
| | | Defect ID | | | | | | | | |
