# UNIT TEST - ProcessWalletCashoutRequest

| Function Code | WAL-002 | Function Name | | ProcessWalletCashoutRequestAsync |
|---------------|---------|---------------|---|---------------------------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 55 | **Lack of test cases** | | |
| **Test requirement** | Verify wallet cashout request processing | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 10 | 2 | 7 | 1 | 10 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 | UTCID09 | UTCID10 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O | O | O |
| | **dto** | | | | | | | | | | | | |
| | | Valid WalletProcessCreateDTO | | O | O | | | | | | | | |
| | | null | | | | O | | | | | | | |
| | **userId** | | | | | | | | | | | | |
| | | User with pending cashout | | O | O | | | | | | | | |
| | | User without cashout request | | | | | O | | | | | | |
| | **bankAccount** | | | | | | | | | | | | |
| | | Valid bank account | | O | O | | | | | | | | |
| | | Bank account not found | | | | | | O | | | | | |
| | **status** | | | | | | | | | | | | |
| | | Completed | | O | | | | | | | | | |
| | | Cancelled | | | O | | | | | | | | |
| | | Pending (invalid) | | | | | | | O | | | | |
| | **gatewayPaymentId** | | | | | | | | | | | | |
| | | Provided (Completed) | | O | | | | | | | | | |
| | | null (Completed) | | | | | | | | O | | | |
| | | Provided (Cancelled) | | | B | | | | | | | | |
| | **cancelReason** | | | | | | | | | | | | |
| | | Provided (Cancelled) | | | O | | | | | | | | |
| | | null (Cancelled) | | | | | | | | | O | | |
| | **wallet balance update** | | | | | | | | | | | | |
| | | Sufficient balance | | O | | | | | | | | | |
| | | Balance already deducted | | | | | | | | | | O | |
| | **staffId** | | | | | | | | | | | | |
| | | Valid staff ID | | O | O | | | | | | | | |
| | | Invalid staff ID | | | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | | | |
| | | T | | O | O | | | | | | | | |
| | | F | | | | O | O | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | | | | |
| | | ArgumentNullException | | | | O | | | | | | | |
| | | KeyNotFoundException | | | | | O | O | | | | | |
| | | InvalidOperationException | | | | | | | O | O | O | O | O |
| **Log message** | | | | | | | | | | | | | |
| | | "Cashout completed successfully" | | O | | | | | | | | | |
| | | "Cashout cancelled" | | | O | | | | | | | | |
| | | "dto rỗng" | | | | O | | | | | | | |
| | | "Chưa có yêu cầu rút tiền" | | | | | O | | | | | | |
| | | "Tài khoản ngân hàng không tồn tại" | | | | | | O | | | | | |
| | | "Trạng thái không thể là Pending" | | | | | | | O | | | | |
| | | "Mã giao dịch phải tồn tại" | | | | | | | | O | | | |
| | | "Lý do hủy phải tồn tại" | | | | | | | | | O | | |
| | | "Balance already processed" | | | | | | | | | | O | |
| | | "Invalid staff ID" | | | | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | N | A | A | A | A | A | A | A | B |
| | | Passed/Failed | | | | | | | | | | | |
| | | Executed Date | | | | | | | | | | | |
| | | Defect ID | | | | | | | | | | | |
