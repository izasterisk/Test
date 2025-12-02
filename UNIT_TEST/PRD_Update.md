# UNIT TEST - UpdateProduct

| Function Code | PRD-001 | Function Name | | UpdateAsync |
|---------------|---------|---------------|---|-------------|
| **Created By** | | **Executed By** | | |
| **Lines of code** | 60 | **Lack of test cases** | | |
| **Test requirement** | Verify product update with images | | | |
| **Passed** | | **Failed** | **Untested** | **N/A/B** | | | **Total Test Cases** |
| 0 | | 0 | 8 | 1 | 5 | 2 | 8 |

---

| Condition | Precondition | | | UTCID01 | UTCID02 | UTCID03 | UTCID04 | UTCID05 | UTCID06 | UTCID07 | UTCID08 |
|-----------|--------------|---|---|---------|---------|---------|---------|---------|---------|---------|---------|
| | | Can connect with server | | O | O | O | O | O | O | O | O |
| | **productId** | | | | | | | | | | |
| | | Valid product ID | | O | | | | | | | |
| | | Non-existent ID | | | O | | | | | | |
| | **dto** | | | | | | | | | | |
| | | Valid ProductUpdateDTO | | O | | | | | | | |
| | | null | | | | O | | | | | |
| | **categoryId** | | | | | | | | | | |
| | | Valid category ID | | O | | | | | | | |
| | | Non-existent category | | | | | O | | | | |
| | **vendorId** | | | | | | | | | | |
| | | Valid vendor ID | | O | | | | | | | |
| | | Non-existent vendor | | | | | | O | | | |
| | **unitPrice** | | | | | | | | | | |
| | | Valid price (> 0) | | O | | | | | | | |
| | | Zero price | | | | | | | O | | |
| | | Negative price | | | | | | | | O | |
| | **addImages** | | | | | | | | | | |
| | | Valid images list | | O | | | | | | | |
| | | Empty list | | O | | | | | | | |
| | **removeImagePublicIds** | | | | | | | | | | |
| | | Valid public IDs | | O | | | | | | | |
| | | Invalid public ID | | | | | | | | | O |
| **Confirm** | **Return** | | | | | | | | | | |
| | | T | | O | | | | | | | |
| | | F | | | O | O | O | O | O | O | O |
| **Exception** | | | | | | | | | | | |
| | | KeyNotFoundException | | | O | | O | O | | | |
| | | ArgumentNullException | | | | O | | | | | |
| | | InvalidOperationException | | | | | | | O | O | O |
| **Log message** | | | | | | | | | | | |
| | | "Product updated successfully" | | O | | | | | | | |
| | | "Product không tồn tại" | | | O | | | | | | |
| | | "dto is null" | | | | O | | | | | |
| | | "Category not found" | | | | | O | | | | |
| | | "Vendor not found" | | | | | | O | | | |
| | | "Price must be > 0" | | | | | | | O | O | |
| | | "Image not found" | | | | | | | | | O |
| **Result** | | Type(N : Normal, A : Abnormal, B : Boundary) | | N | A | A | A | A | B | B | A |
| | | Passed/Failed | | | | | | | | | |
| | | Executed Date | | | | | | | | | |
| | | Defect ID | | | | | | | | | |
