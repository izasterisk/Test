# UNIT TEST - CreateFarmProfile

| Function Code | FP-001 | Function Name | | CreateFarmProfileAsync |
|---------------|--------|---------------|---|------------------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 50 | **Lack of test cases** | | |
| **Test requirement** | Verify farm profile creation with address and crops | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 10 | 1 | 7 | 2 | 10 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 | UTCID09 | UTCID10 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O | O | O |
| | **dto** | | | | | | | | | | | | |
| | | Valid FarmProfileCreateDto | | O | | | | | | | | | |
| | | null | | | O | | | | | | | | |
| | **currentUserId** | | | | | | | | | | | | |
| | | Valid user ID | | O | | | | | | | | | |
| | | Non-existent user | | | | O | | | | | | | |
| | **farmName** | | | | | | | | | | | | |
| | | Valid farm name | | O | | | | | | | | | |
| | | Empty farm name | | | | | O | | | | | | |
| | **crops** | | | | | | | | | | | | |
| | | Valid crops list | | O | | | | | | | | | |
| | | Duplicate crop name + plantingDate | | | | | | O | | | | | |
| | | Invalid crop combination | | | | | | | O | | | | |
| | | Invalid crop status | | | | | | | | O | | | |
| | | Future planting date | | | | | | | | | O | | |
| | | Empty crops list | | | | | | | | | | O | |
| | **address** | | | | | | | | | | | | |
| | | Valid address | | O | | | | | | | | | |
| | | Missing required address fields | | | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | | | |
| | | T | | O | | | | | | | | O | |
| | | F | | | O | O | O | O | O | O | O | | O |
| **Exception** | | | | | | | | | | | | | |
| | | ArgumentNullException | | | O | | | | | | | | |
| | | KeyNotFoundException | | | | O | | | | | | | |
| | | ArgumentException | | | | | O | O | O | O | O | | O |
| **Log message** | | | | | | | | | | | | | |
| | | "Farm profile created" | | O | | | | | | | | O | |
| | | "dto rỗng" | | | O | | | | | | | | |
| | | "User not found" | | | | O | | | | | | | |
| | | "Farm name required" | | | | | O | | | | | | |
| | | "Cây trồng bị trùng lặp" | | | | | | O | | | | | |
| | | "Invalid crop combination" | | | | | | | O | | | | |
| | | "Trạng thái cây trồng không hợp lệ" | | | | | | | | O | | | |
| | | "Ngày trồng không được lớn hơn ngày hiện tại" | | | | | | | | | O | | |
| | | "Missing address fields" | | | | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | A | A | B | N | A |
| | | Passed/Failed | | | | | | | | | | | |
| | | Executed Date | | | | | | | | | | | |
| | | Defect ID | | | | | | | | | | | |
