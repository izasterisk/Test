# UNIT TEST - UpdateCartItemQuantity

| Function Code | CART-002 | Function Name | | UpdateCartItemQuantityAsync |
|---------------|----------|---------------|---|----------------------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 35 | **Lack of test cases** | | |
| **Test requirement** | Verify updating cart item quantity | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 6 | 1 | 4 | 1 | 6 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O |
| | **dto** | | | | | | | | |
| | | Valid CartDTO | | O | | | | | |
| | | null | | | O | | | | |
| | **userId** | | | | | | | | |
| | | Valid user ID with cart | | O | | | | | |
| | | User without cart | | | | O | | | |
| | **productId** | | | | | | | | |
| | | Product exists in cart | | O | | | | | |
| | | Product not in cart | | | | | O | | |
| | **quantity** | | | | | | | | |
| | | Valid quantity (> 0) | | O | | | | | |
| | | Zero (delete item) | | | | | | O | |
| | | Very large quantity | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | |
| | | T | | O | | | | O | |
| | | F | | | O | O | O | | O |
| **Exception** | | | | | | | | | |
| | | ArgumentNullException | | | O | | | | |
| | | InvalidOperationException | | | | O | O | | O |
| **Log message** | | | | | | | | | |
| | | "Cart updated successfully" | | O | | | | | |
| | | "Item removed from cart" | | | | | | O | |
| | | "dto is null" | | | O | | | | |
| | | "Cart not found" | | | | O | | | |
| | | "Product not in cart" | | | | | O | | |
| | | "Quantity exceeds stock" | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | B | A |
| | | Passed/Failed | | | | | | | |
| | | Executed Date | | | | | | | |
| | | Defect ID | | | | | | | |
