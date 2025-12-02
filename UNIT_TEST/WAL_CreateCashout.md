# UNIT TEST - CreateWalletCashoutRequest

| Function Code | WAL-001 | Function Name | | CreateWalletCashoutRequestAsync |
|---------------|---------|---------------|---|--------------------------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 35 | **Lack of test cases** | | |
| **Test requirement** | Verify wallet cashout request creation | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 8 | 1 | 5 | 2 | 8 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O |
| | **dto** | | | | | | | | | | |
| | | Valid WalletCashoutRequestCreateDTO | | O | | | | | | | |
| | | null | | | O | | | | | | |
| | **userId** | | | | | | | | | | |
| | | Valid vendor ID (qualified) | | O | | | | | | | |
| | | Non-existent user | | | | O | | | | | |
| | | Non-vendor user | | | | | O | | | | |
| | **bankAccountId** | | | | | | | | | | |
| | | User's bank account | | O | | | | | | | |
| | | Other user's bank account | | | | | | O | | | |
| | **amount** | | | | | | | | | | |
| | | Valid amount (<= balance) | | O | | | | | | | |
| | | Amount > balance | | | | | | | O | | |
| | | Zero amount | | | | | | | | O | |
| | | Negative amount | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | |
| | | T | | O | | | | | | | |
| | | F | | | O | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | | |
| | | ArgumentNullException | | | O | | | | | | |
| | | KeyNotFoundException | | | | O | O | | | | |
| | | UnauthorizedAccessException | | | | | | O | | | |
| | | InvalidOperationException | | | | | | | O | O | O |
| **Log message** | | | | | | | | | | | |
| | | "Cashout request created" | | O | | | | | | | |
| | | "dto rỗng" | | | O | | | | | | |
| | | "Người dùng không tồn tại hoặc không đủ điều kiện" | | | | O | O | | | | |
| | | "Tài khoản ngân hàng không thuộc về người dùng" | | | | | | O | | | |
| | | "Số dư không đủ" | | | | | | | O | | |
| | | "Amount must be > 0" | | | | | | | | O | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | A | B | B |
| | | Passed/Failed | | | | | | | | | |
| | | Executed Date | | | | | | | | | |
| | | Defect ID | | | | | | | | | |
