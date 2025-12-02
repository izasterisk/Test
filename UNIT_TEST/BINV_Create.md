# UNIT TEST - CreateBatchInventory

| Function Code | BINV-001 | Function Name | | CreateAsync |
|---------------|----------|---------------|---|-------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 45 | **Lack of test cases** | | |
| **Test requirement** | Verify batch inventory creation | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 9 | 1 | 6 | 2 | 9 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 | UTCID09 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O | O |
| | **productId** | | | | | | | | | | | |
| | | Valid product ID | | O | | | | | | | | |
| | | Non-existent product | | | O | | | | | | | |
| | **vendorId** | | | | | | | | | | | |
| | | Valid vendor ID | | O | | | | | | | | |
| | | Non-existent user | | | | O | | | | | | |
| | | User not a vendor | | | | | O | | | | | |
| | **product category** | | | | | | | | | | | |
| | | SerialRequired = true | | O | | | | | | | | |
| | | SerialRequired = false | | | | | | O | | | | |
| | **quantity** | | | | | | | | | | | |
| | | Valid quantity (> 0) | | O | | | | O | | | | |
| | | Zero quantity (serial required) | | | | | | | O | | | |
| | | Negative quantity | | | | | | | | O | | |
| | **lotNumber** | | | | | | | | | | | |
| | | Valid lot number | | O | | | | | | | | |
| | | Empty lot number (serial required) | | | | | | | | | O | |
| | | Empty lot number (serial not required) | | | | | | O | | | | |
| | **stock update** | | | | | | | | | | | |
| | | Product stock updated | | O | | | | O | | | | |
| | | Large quantity update | | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | | |
| | | T | | O | | | | O | | | | O |
| | | F | | | O | O | O | | O | O | O | |
| **Exception** | | | | | | | | | | | | |
| | | KeyNotFoundException | | | O | | | | | | | |
| | | ArgumentException | | | | O | O | | O | O | O | |
| **Log message** | | | | | | | | | | | | |
| | | "Batch inventory created" | | O | | | | O | | | | O |
| | | "Không tìm thấy sản phẩm" | | | O | | | | | | | |
| | | "Không tìm thấy người dùng" | | | | O | | | | | | |
| | | "Người dùng không phải là nhà cung cấp" | | | | | O | | | | | |
| | | "Quantity phải > 0 (serial)" | | | | | | | O | | | |
| | | "Quantity cannot be negative" | | | | | | | | O | | |
| | | "LotNumber bắt buộc (serial)" | | | | | | | | | O | |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | N | A | B | A | B |
| | | Passed/Failed | | | | | | | | | | |
| | | Executed Date | | | | | | | | | | |
| | | Defect ID | | | | | | | | | | |
