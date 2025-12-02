# UNIT TEST - ChangeProductRegistrationStatus

| Function Code | PREG-002 | Function Name | | ChangeStatusAsync |
|---------------|----------|---------------|---|-------------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 90 | **Lack of test cases** | | |
| **Test requirement** | Verify product registration status change (approve/reject) | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 9 | 2 | 6 | 1 | 9 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 | UTCID09 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O | O |
| | **registrationId** | | | | | | | | | | | |
| | | Valid registration ID | | O | O | | | | | | | |
| | | Non-existent ID | | | | O | | | | | | |
| | **current status** | | | | | | | | | | | |
| | | Pending | | O | O | | | | | | | |
| | | Already approved | | | | | O | | | | | |
| | | Already rejected | | | | | | O | | | | |
| | **new status** | | | | | | | | | | | |
| | | Approved | | O | | | | | | | | |
| | | Rejected | | | O | | | | | | | |
| | | Invalid status | | | | | | | O | | | |
| | **approvedBy** | | | | | | | | | | | |
| | | Valid staff ID | | O | | | | | | | | |
| | | null (when Approved) | | | | | | | | O | | |
| | **rejectionReason** | | | | | | | | | | | |
| | | Valid reason (when Reject) | | | O | | | | | | | |
| | | null (when Reject) | | | | | | | | | O | |
| | **product creation** | | | | | | | | | | | |
| | | Product created on approve | | O | | | | | | | | |
| | | No product on reject | | | O | | | | | | | |
| | **certificates** | | | | | | | | | | | |
| | | Certs verified on approve | | O | | | | | | | | |
| | | Certs rejected on reject | | | O | | | | | | | |
| | | No certs to process | | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | | |
| | | T | | O | O | | | | | | | O |
| | | F | | | | O | O | O | O | O | O | |
| **Exception** | | | | | | | | | | | | |
| | | InvalidOperationException | | | | O | O | O | O | O | O | |
| **Log message** | | | | | | | | | | | | |
| | | "Registration approved" | | O | | | | | | | | |
| | | "Registration rejected" | | | O | | | | | | | |
| | | "Đơn đăng ký không tồn tại" | | | | O | | | | | | |
| | | "Đơn đã được duyệt trước đó" | | | | | O | | | | | |
| | | "Đơn đã bị từ chối trước đó" | | | | | | O | | | | |
| | | "Trạng thái không hợp lệ" | | | | | | | O | | | |
| | | "ApprovedBy required" | | | | | | | | O | | |
| | | "Rejection reason required" | | | | | | | | | O | |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | N | A | A | A | A | A | A | B |
| | | Passed/Failed | | | | | | | | | | |
| | | Executed Date | | | | | | | | | | |
| | | Defect ID | | | | | | | | | | |
