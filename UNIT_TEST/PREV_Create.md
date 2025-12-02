# UNIT TEST - CreateProductReview

| Function Code | PREV-001 | Function Name | | CreateProductReviewAsync |
|---------------|----------|---------------|---|--------------------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 55 | **Lack of test cases** | | |
| **Test requirement** | Verify product review creation | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 10 | 1 | 7 | 2 | 10 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 | UTCID09 | UTCID10 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O | O | O |
| | **customerId** | | | | | | | | | | | | |
| | | Valid customer ID | | O | | | | | | | | | |
| | | Non-existent customer | | | O | | | | | | | | |
| | **orderId** | | | | | | | | | | | | |
| | | Valid order ID | | O | | | | | | | | | |
| | | Non-existent order | | | | O | | | | | | | |
| | | Order not belongs to customer | | | | | O | | | | | | |
| | **order status** | | | | | | | | | | | | |
| | | Paid/Shipped/Delivered | | O | | | | | | | | | |
| | | Pending/Processing | | | | | | O | | | | | |
| | | Cancelled/Refunded | | | | | | | O | | | | |
| | **productId** | | | | | | | | | | | | |
| | | Product in order | | O | | | | | | | | | |
| | | Product not in order | | | | | | | | O | | | |
| | **existing review** | | | | | | | | | | | | |
| | | No existing review | | O | | | | | | | | | |
| | | Already reviewed | | | | | | | | | O | | |
| | **rating** | | | | | | | | | | | | |
| | | Valid rating (1-5) | | O | | | | | | | | | |
| | | Invalid rating (0 or > 5) | | | | | | | | | | O | |
| | **images** | | | | | | | | | | | | |
| | | Valid images list | | O | | | | | | | | | |
| | | Empty images | | | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | | | |
| | | T | | O | | | | | | | | | O |
| | | F | | | O | O | O | O | O | O | O | O | |
| **Exception** | | | | | | | | | | | | | |
| | | KeyNotFoundException | | | O | O | | | | | | | |
| | | UnauthorizedAccessException | | | | | O | | | | | | |
| | | InvalidOperationException | | | | | | O | O | O | O | O | |
| **Log message** | | | | | | | | | | | | | |
| | | "Review created successfully" | | O | | | | | | | | | O |
| | | "Customer not found" | | | O | | | | | | | | |
| | | "Đơn hàng không tồn tại" | | | | O | | | | | | | |
| | | "Bạn không có quyền đánh giá đơn hàng này" | | | | | O | | | | | | |
| | | "Chỉ có thể đánh giá sau khi thanh toán" | | | | | | O | O | | | | |
| | | "Sản phẩm không có trong đơn hàng" | | | | | | | | O | | | |
| | | "Bạn đã đánh giá sản phẩm này rồi" | | | | | | | | | O | | |
| | | "Invalid rating value" | | | | | | | | | | O | |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | A | A | A | B | N |
| | | Passed/Failed | | | | | | | | | | | |
| | | Executed Date | | | | | | | | | | | |
| | | Defect ID | | | | | | | | | | | |
