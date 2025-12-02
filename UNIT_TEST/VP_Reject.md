# UNIT TEST - RejectVendorProfile

| Function Code | VP-003 | Function Name | | RejectAsync |
|---------------|--------|---------------|---|-------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 35 | **Lack of test cases** | | |
| **Test requirement** | Verify vendor profile rejection process | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 7 | 1 | 5 | 1 | 7 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O |
| | **vendorProfileId** | | | | | | | | | |
| | | Valid profile ID | | O | | | | | | |
| | | Non-existent ID | | | O | | | | | |
| | **vendor profile status** | | | | | | | | | |
| | | Pending status | | O | | | | | | |
| | | Already verified | | | | O | | | | |
| | | Already rejected | | | | | O | | | |
| | **user** | | | | | | | | | |
| | | User exists | | O | | | | | | |
| | | User not found | | | | | | O | | |
| | **verifiedBy** | | | | | | | | | |
| | | Valid staff ID | | O | | | | | | |
| | | Invalid staff ID | | | | | | | O | |
| | **rejectionReason** | | | | | | | | | |
| | | Valid reason | | O | | | | | | |
| | | null/empty reason | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | |
| | | T | | O | | | | | | |
| | | F | | | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | |
| | | InvalidOperationException | | | O | O | O | O | O | O |
| **Log message** | | | | | | | | | | |
| | | "Vendor profile rejected" | | O | | | | | | |
| | | "Hồ sơ vendor không tồn tại" | | | O | | | | | |
| | | "Profile already verified" | | | | O | | | | |
| | | "Profile already rejected" | | | | | O | | | |
| | | "User not found" | | | | | | O | | |
| | | "Invalid verifier ID" | | | | | | | O | |
| | | "Rejection reason required" | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | A | B |
| | | Passed/Failed | | | | | | | | |
| | | Executed Date | | | | | | | | |
| | | Defect ID | | | | | | | | |
