# Feature_Product - Product Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Product |
| **Test requirement** | API and design are available |
| **Number of TCs** | 16 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 16 | 0 |
| Round 2 | 0 | 0 | 16 | 0 |
| Round 3 | 0 | 0 | 16 | 0 |

---

## Test Cases

### Product List & Detail

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PROD01 | Get all products with pagination | 1. Call GET `/api/Product?page=1&pageSize=20`<br>2. Check response | - List of products returned<br>- Pagination info included<br>- Status 200 OK | Products exist in DB |
| PROD02 | Get product by ID | 1. Call GET `/api/Product/{id}` with valid ID<br>2. Check response | - Product detail returned<br>- Includes images, specs<br>- Status 200 OK | Product exists |
| PROD03 | Get product with non-existent ID | 1. Call GET `/api/Product/99999` | - Status 404 Not Found | None |
| PROD04 | Get products by category | 1. Call GET `/api/Product/category/{categoryId}`<br>2. Check response | - Only products in category returned<br>- Status 200 OK | Category with products exists |
| PROD05 | Get products by vendor | 1. Call GET `/api/Product/vendor/{vendorId}`<br>2. Check response | - Only vendor's products returned<br>- Status 200 OK | Vendor with products exists |

---

### Product Update

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PROD06 | Update product info | 1. Call PUT `/api/Product/{id}`<br>2. Send updated data in body<br>3. Check response | - Product updated<br>- Status 200 OK | Product exists, logged in |
| PROD07 | Update product with add/remove images | 1. Call PUT `/api/Product/{id}`<br>2. Include addImages and removeImagePublicIds<br>3. Check response | - New images added<br>- Old images removed<br>- Status 200 OK | Product exists with images |
| PROD08 | Update commission rate | 1. Call PATCH `/api/Product/{id}/emission`<br>2. Send commissionRate in body | - Commission rate updated<br>- Status 204 No Content | Product exists |

---

### Product Category

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PROD09 | Get all categories | 1. Login<br>2. Call GET `/api/ProductCategory` | - List of all categories<br>- Status 200 OK | Logged in |
| PROD10 | Create new category | 1. Login<br>2. Call POST `/api/ProductCategory`<br>3. Send category name | - Category created<br>- Status 201 Created | Logged in |
| PROD11 | Update category | 1. Login<br>2. Call PATCH `/api/ProductCategory/{id}`<br>3. Send updated name | - Category updated<br>- Status 200 OK | Category exists |
| PROD12 | Create child category | 1. Login<br>2. Call POST `/api/ProductCategory`<br>3. Send name with parentId | - Child category created<br>- Linked to parent | Parent category exists |

---

### Product Review

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PROD13 | Create product review | 1. Login as Customer<br>2. Call POST `/api/ProductReview`<br>3. Upload form with rating, content, images | - Review created<br>- Status 201 Created | Purchased product, logged in as Customer |
| PROD14 | Get reviews by product ID | 1. Call GET `/api/ProductReview/product/{productId}` | - List of reviews returned<br>- Status 200 OK | Product has reviews |
| PROD15 | Update own review | 1. Login as Customer<br>2. Call PUT `/api/ProductReview/{id}`<br>3. Update rating/content | - Review updated<br>- Status 200 OK | Own review exists |
| PROD16 | Delete own review | 1. Login as Customer<br>2. Call DELETE `/api/ProductReview/{id}` | - Review deleted<br>- Status 204 No Content | Own review exists |
