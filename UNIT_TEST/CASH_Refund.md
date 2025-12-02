# UNIT TEST - CreateCashoutRefund

| Function Code | CASH-001 | Function Name | | CreateCashoutRefundAsync |
|---------------|----------|---------------|---|--------------------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 90 | **Lack of test cases** | | |
| **Test requirement** | Verify refund cashout creation for approved refund requests | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 12 | 1 | 9 | 2 | 12 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 | UTCID09 | UTCID10 | UTCID11 | UTCID12 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O | O | O | O | O |
| | **dtos** | | | | | | | | | | | | | | |
| | | Valid RefundCreateDTO | | O | | | | | | | | | | | |
| | | null | | | O | | | | | | | | | | |
| | **requestId** | | | | | | | | | | | | | | |
| | | Valid request ID | | O | | | | | | | | | | | |
| | | Non-existent request | | | | O | | | | | | | | | |
| | **request status** | | | | | | | | | | | | | | |
| | | Approved RefundRequest | | O | | | | | | | | | | | |
| | | Not approved | | | | | O | | | | | | | | |
| | | Not RefundRequest type | | | | | | O | | | | | | | |
| | **order** | | | | | | | | | | | | | | |
| | | Order belongs to requester | | O | | | | | | | | | | | |
| | | Order not belongs to requester | | | | | | | O | | | | | | |
| | | Order already refunded | | | | | | | | O | | | | | |
| | | Order not delivered | | | | | | | | | O | | | | |
| | | Order delivered > 7 days | | | | | | | | | | O | | | |
| | **refundAmount** | | | | | | | | | | | | | | |
| | | Valid amount (<= order total) | | O | | | | | | | | | | | |
| | | Amount > order total | | | | | | | | | | | O | | |
| | **orderDetails** | | | | | | | | | | | | | | |
| | | Valid order details | | O | | | | | | | | | | | |
| | | Duplicate orderDetailId | | | | | | | | | | | | O | |
| | **serialNumber** | | | | | | | | | | | | | | |
| | | Valid serial (when required) | | O | | | | | | | | | | | |
| | | Duplicate serial | | | | | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | | | | | |
| | | T | | O | | | | | | | | | | | |
| | | F | | | O | O | O | O | O | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | | | | | | |
| | | ArgumentNullException | | | O | | | | | | | | | | |
| | | KeyNotFoundException | | | | O | | | | | | | | | |
| | | InvalidDataException | | | | | O | O | | O | O | O | O | | |
| | | UnauthorizedAccessException | | | | | | | O | | | | | | |
| | | InvalidOperationException | | | | | | | | | | | | | O | O |
| **Log message** | | | | | | | | | | | | | | | |
| | | "Refund created successfully" | | O | | | | | | | | | | | |
| | | "dtos rỗng" | | | O | | | | | | | | | | |
| | | "Request not found" | | | | O | | | | | | | | | |
| | | "Yêu cầu không đủ điều kiện để hoàn tiền" | | | | | O | O | | | | | | | |
| | | "Yêu cầu không thuộc về người đặt hàng" | | | | | | | O | | | | | | |
| | | "Đơn hàng đã được hoàn tiền" | | | | | | | | O | | | | | |
| | | "Đơn hàng chưa được giao" | | | | | | | | | O | | | | |
| | | "Quá 7 ngày kể từ khi giao" | | | | | | | | | | O | | | |
| | | "Số tiền hoàn vượt quá" | | | | | | | | | | | O | | |
| | | "OrderDetailId bị lặp" | | | | | | | | | | | | O | |
| | | "Serial bị trùng" | | | | | | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | A | A | A | B | A | A | A |
| | | Passed/Failed | | | | | | | | | | | | | |
| | | Executed Date | | | | | | | | | | | | | |
| | | Defect ID | | | | | | | | | | | | | |
