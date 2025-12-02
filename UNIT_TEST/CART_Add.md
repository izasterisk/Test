# UNIT TEST - AddToCart

| Function Code | CART-001 | Function Name | | AddToCartAsync |
|---------------|----------|---------------|---|----------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 30 | **Lack of test cases** | | |
| **Test requirement** | Verify adding product to cart | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 7 | 1 | 4 | 2 | 7 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O |
| | **dto** | | | | | | | | | |
| | | Valid CartDTO | | O | | | | | | |
| | | null | | | O | | | | | |
| | **userId** | | | | | | | | | |
| | | Valid user ID | | O | | | | | | |
| | | Non-existent user ID | | | | O | | | | |
| | **productId** | | | | | | | | | |
| | | Valid product ID | | O | | | | | | |
| | | Non-existent product ID | | | | | O | | | |
| | | Product already in cart | | | | | | O | | |
| | **quantity** | | | | | | | | | |
| | | Valid quantity (> 0) | | O | | | | | | |
| | | Zero quantity | | | | | | | O | |
| | | Negative quantity | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | |
| | | T | | O | | | | | | |
| | | F | | | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | |
| | | ArgumentNullException | | | O | | | | | |
| | | KeyNotFoundException | | | | O | O | | | |
| | | InvalidOperationException | | | | | | O | | |
| | | ArgumentOutOfRangeException | | | | | | | O | O |
| **Log message** | | | | | | | | | | |
| | | "Product added to cart" | | O | | | | | | |
| | | "dto is null" | | | O | | | | | |
| | | "User not found" | | | | O | | | | |
| | | "Product not found" | | | | | O | | | |
| | | "Product already in cart" | | | | | | O | | |
| | | "Quantity must be > 0" | | | | | | | O | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | B | B |
| | | Passed/Failed | | | | | | | | |
| | | Executed Date | | | | | | | | |
| | | Defect ID | | | | | | | | |
