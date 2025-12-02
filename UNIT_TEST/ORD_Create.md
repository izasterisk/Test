# UNIT TEST - CreateOrder

| Function Code | ORD-001 | Function Name | | CreateOrderAsync |
|---------------|---------|---------------|---|------------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 80 | **Lack of test cases** | | |
| **Test requirement** | Verify order creation from order preview | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 10 | 1 | 7 | 2 | 10 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 | UTCID09 | UTCID10 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O | O | O |
| | **dto** | | | | | | | | | | | | |
| | | Valid OrderCreateDTO | | O | | | | | | | | | |
| | | null | | | O | | | | | | | | |
| | **orderPreviewId** | | | | | | | | | | | | |
| | | Valid GUID (exists in cache) | | O | | | | | | | | | |
| | | Expired/Invalid GUID | | | | O | | | | | | | |
| | **priceTableId** | | | | | | | | | | | | |
| | | Valid shipping service ID | | O | | | | | | | | | |
| | | Invalid service ID | | | | | O | | | | | | |
| | **user** | | | | | | | | | | | | |
| | | Active, IsVerified=true | | O | | | | | | | | | |
| | | User not found | | | | | | O | | | | | |
| | | Inactive/Deleted | | | | | | | O | | | | |
| | **product availability** | | | | | | | | | | | | |
| | | Sufficient stock | | O | | | | | | | | | |
| | | Product not exists | | | | | | | | O | | | |
| | | Insufficient stock | | | | | | | | | O | | |
| | **order details** | | | | | | | | | | | | |
| | | Valid order details | | O | | | | | | | | | |
| | | Empty order details | | | | | | | | | | O | |
| | | Duplicate product ID | | | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | | | |
| | | T | | O | | | | | | | | | |
| | | F | | | O | O | O | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | | | | |
| | | ArgumentNullException | | | O | | | | | | | | |
| | | KeyNotFoundException | | | | O | O | O | | O | | | |
| | | InvalidOperationException | | | | | | | O | | O | O | O |
| **Log message** | | | | | | | | | | | | | |
| | | "Order created successfully" | | O | | | | | | | | | |
| | | "dto rỗng" | | | O | | | | | | | | |
| | | "Order preview expired" | | | | O | | | | | | | |
| | | "Shipping service not found" | | | | | O | | | | | | |
| | | "User not found" | | | | | | O | | | | | |
| | | "User inactive or deleted" | | | | | | | O | | | | |
| | | "Product not exists" | | | | | | | | O | | | |
| | | "Insufficient stock" | | | | | | | | | O | | |
| | | "Empty order details" | | | | | | | | | | O | |
| | | "Duplicate product ID" | | | | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | A | A | A | B | A |
| | | Passed/Failed | | | | | | | | | | | |
| | | Executed Date | | | | | | | | | | | |
| | | Defect ID | | | | | | | | | | | |
