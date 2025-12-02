# UNIT TEST - CreateProductRegistration

| Function Code | PREG-001 | Function Name | | CreateAsync |
|---------------|----------|---------------|---|-------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 100 | **Lack of test cases** | | |
| **Test requirement** | Verify product registration creation with certificates | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 10 | 1 | 7 | 2 | 10 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 | UTCID09 | UTCID10 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O | O | O |
| | **vendorId** | | | | | | | | | | | | |
| | | Valid vendor ID | | O | | | | | | | | | |
| | | Non-existent vendor | | | O | | | | | | | | |
| | **categoryId** | | | | | | | | | | | | |
| | | Valid category ID | | O | | | | | | | | | |
| | | Non-existent category | | | | O | | | | | | | |
| | | Parent category (invalid) | | | | | O | | | | | | |
| | **energyEfficiencyRating** | | | | | | | | | | | | |
| | | Valid rating (0-5) | | O | | | | | | | | | |
| | | Invalid rating (> 5) | | | | | | O | | | | | |
| | | Negative rating | | | | | | | O | | | | |
| | **dimensionsCm** | | | | | | | | | | | | |
| | | Valid dimensions | | O | | | | | | | | | |
| | | Invalid dimensions | | | | | | | | O | | | |
| | **certificationName/Code** | | | | | | | | | | | | |
| | | Valid cert data | | O | | | | | | | | | |
| | | Mismatched count | | | | | | | | | O | | |
| | **addCertificates files** | | | | | | | | | | | | |
| | | Matching files count | | O | | | | | | | | | |
| | | Mismatched files count | | | | | | | | | | O | |
| | **addImages** | | | | | | | | | | | | |
| | | Valid images list | | O | | | | | | | | | |
| | | Empty images | | | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | | | |
| | | T | | O | | | | | | | | | O |
| | | F | | | O | O | O | O | O | O | O | O | |
| **Exception** | | | | | | | | | | | | | |
| | | InvalidOperationException | | | O | O | O | O | O | O | O | O | |
| **Log message** | | | | | | | | | | | | | |
| | | "Registration created" | | O | | | | | | | | | O |
| | | "Vendor không tồn tại" | | | O | | | | | | | | |
| | | "Category không tồn tại" | | | | O | | | | | | | |
| | | "Category không thể là parent" | | | | | O | | | | | | |
| | | "Rating phải từ 0 đến 5" | | | | | | O | O | | | | |
| | | "Kích thước không hợp lệ" | | | | | | | | O | | | |
| | | "Tên và mã chứng chỉ không khớp" | | | | | | | | | O | | |
| | | "File chứng chỉ không khớp" | | | | | | | | | | O | |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | B | B | A | A | A | N |
| | | Passed/Failed | | | | | | | | | | | |
| | | Executed Date | | | | | | | | | | | |
| | | Defect ID | | | | | | | | | | | |
