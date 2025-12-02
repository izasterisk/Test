# UNIT TEST - ProcessOrder

| Function Code | ORD-002 | Function Name | | ProcessOrderAsync |
|---------------|---------|---------------|---|-------------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 70 | **Lack of test cases** | | |
| **Test requirement** | Verify order status update and processing | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 12 | 1 | 9 | 2 | 12 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 | UTCID09 | UTCID10 | UTCID11 | UTCID12 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O | O | O | O | O |
| | **dto** | | | | | | | | | | | | | | |
| | | Valid OrderUpdateDTO | | O | | | | | | | | | | | |
| | | null | | | O | | | | | | | | | | |
| | **orderId** | | | | | | | | | | | | | | |
| | | Valid order ID | | O | | | | | | | | | | | |
| | | Non-existent order ID | | | | O | | | | | | | | | |
| | **user permission** | | | | | | | | | | | | | | |
| | | Owner of order | | O | | | | | | | | | | | |
| | | Admin/Staff | | | | | O | | | | | | | | |
| | | Other customer | | | | | | O | | | | | | | |
| | **current status** | | | | | | | | | | | | | | |
| | | Pending | | O | | | | | | | | | | | |
| | | Processing | | | | | | | | O | | | | | |
| | | Shipped | | | | | | | | | O | | | | |
| | **new status** | | | | | | | | | | | | | | |
| | | Processing (by Staff) | | | | | O | | | | | | | | |
| | | Cancelled (by Customer) | | O | | | | | | | | | | | |
| | | Cancelled (non-Pending) | | | | | | | O | | | | | | |
| | | Delivered (by Customer) | | | | | | | | | O | | | | |
| | | Paid (invalid) | | | | | | | | | | O | | | |
| | **cancelledReason** | | | | | | | | | | | | | | |
| | | Provided with Cancel status | | O | | | | | | | | | | | |
| | | Provided without Cancel status | | | | | | | | | | | O | | |
| | **payment method** | | | | | | | | | | | | | | |
| | | COD | | | | | O | | | | | | | | |
| | | Non-COD to Processing | | | | | | | | | | | | O | |
| | **status transition** | | | | | | | | | | | | | | |
| | | Valid transition | | O | | | | | | | | | | | |
| | | Invalid transition | | | | | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | | | | | |
| | | T | | O | | | O | | | O | O | | | | |
| | | F | | | O | O | | O | O | | | O | O | O | O |
| **Exception** | | | | | | | | | | | | | | | |
| | | ArgumentNullException | | | O | | | | | | | | | | |
| | | KeyNotFoundException | | | | O | | | | | | | | | |
| | | UnauthorizedAccessException | | | | | | O | | | | | | | |
| | | InvalidCastException | | | | | | | O | | | O | | | |
| | | InvalidOperationException | | | | | | | | | | | | O | O | O |
| **Log message** | | | | | | | | | | | | | | | |
| | | "Order updated successfully" | | O | | | O | | | O | O | | | | |
| | | "dto rỗng" | | | O | | | | | | | | | | |
| | | "Order not found" | | | | O | | | | | | | | | |
| | | "Unauthorized access" | | | | | | O | | | | | | | |
| | | "Only Pending can be cancelled" | | | | | | | O | | | | | | |
| | | "Cannot set status to Paid" | | | | | | | | | | O | | | |
| | | "Cancel reason without Cancel status" | | | | | | | | | | | O | | |
| | | "Non-COD cannot be Processing" | | | | | | | | | | | | O | |
| | | "Invalid status transition" | | | | | | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | N | A | A | N | N | A | A | A | B |
| | | Passed/Failed | | | | | | | | | | | | | |
| | | Executed Date | | | | | | | | | | | | | |
| | | Defect ID | | | | | | | | | | | | | |
