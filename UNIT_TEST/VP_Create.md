# UNIT TEST - CreateVendorProfile

| Function Code | VP-001 | Function Name | | CreateAsync |
|---------------|--------|---------------|---|-------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 120 | **Lack of test cases** | | |
| **Test requirement** | Verify vendor profile creation with certificates | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 12 | 1 | 9 | 2 | 12 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 | UTCID09 | UTCID10 | UTCID11 | UTCID12 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O | O | O | O | O |
| | **email** | | | | | | | | | | | | | | |
| | | newvendor@gmail.com | | O | | | | | | | | | | | |
| | | existedactive@gmail.com | | | O | | | | | | | | | | |
| | | existedinactive@gmail.com | | | | O | | | | | | | | | |
| | | null/empty | | | | | O | | | | | | | | |
| | **password** | | | | | | | | | | | | | | |
| | | ValidP@ss123 | | O | | | | | | | | | | | |
| | | null/empty | | | | | | O | | | | | | | |
| | **companyName** | | | | | | | | | | | | | | |
| | | Valid Company Name | | O | | | | | | | | | | | |
| | | null/empty | | | | | | | O | | | | | | |
| | **certificationCode** | | | | | | | | | | | | | | |
| | | Valid codes list | | O | | | | | | | | | | | |
| | | Empty list | | | | | | | | O | | | | | |
| | **certificationName** | | | | | | | | | | | | | | |
| | | Valid names list | | O | | | | | | | | | | | |
| | | Empty list | | | | | | | | | O | | | | |
| | **certificateFiles** | | | | | | | | | | | | | | |
| | | Valid files list | | O | | | | | | | | | | | |
| | | Empty list | | | | | | | | | | O | | | |
| | **count mismatch** | | | | | | | | | | | | | | |
| | | Codes = Names = Files | | O | | | | | | | | | | | |
| | | Codes != Names | | | | | | | | | | | O | | |
| | | Files != Codes | | | | | | | | | | | | O | |
| | **businessRegistrationNumber** | | | | | | | | | | | | | | |
| | | Valid number | | O | | | | | | | | | | | |
| | | Existed number | | | | | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | | | | | |
| | | T | | O | | O | | | | | | | | | |
| | | F | | | O | | O | O | O | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | | | | | | |
| | | InvalidOperationException | | | O | | O | O | O | O | O | O | O | O | O |
| **Log message** | | | | | | | | | | | | | | | |
| | | "Vendor profile created" | | O | | O | | | | | | | | | |
| | | "Email already active" | | | O | | | | | | | | | | |
| | | "Email không được để trống" | | | | | O | | | | | | | | |
| | | "Mật khẩu không được để trống" | | | | | | O | | | | | | | |
| | | "Company name required" | | | | | | | O | | | | | | |
| | | "Thiếu mã chứng chỉ" | | | | | | | | O | | | | | |
| | | "Thiếu tên chứng chỉ" | | | | | | | | | O | | | | |
| | | "Thiếu file chứng chỉ" | | | | | | | | | | O | | | |
| | | "Số lượng không khớp" | | | | | | | | | | | O | O | |
| | | "Business number existed" | | | | | | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | N | A | A | A | A | A | A | A | A | B |
| | | Passed/Failed | | | | | | | | | | | | | |
| | | Executed Date | | | | | | | | | | | | | |
| | | Defect ID | | | | | | | | | | | | | |
