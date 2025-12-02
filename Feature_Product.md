# Feature_Product - Product UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Product |
| **Test requirement** | Marketplace and Product Detail pages available |
| **Number of TCs** | 6 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 6 | 0 |
| Round 2 | 0 | 0 | 6 | 0 |
| Round 3 | 0 | 0 | 6 | 0 |

---

## Test Cases

### Marketplace Page (/marketplace)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PROD01 | View product listing | 1. Open /marketplace page | - Loading spinner shows first<br>- Product grid displays<br>- Each product shows: image, name, price, rating<br>- Pagination shows if many products | Page loaded |
| PROD02 | Search product by name | 1. Go to /marketplace<br>2. Enter "thuốc trừ sâu" in search box<br>3. Press Enter or click search | - Loading shows<br>- Results filtered by keyword<br>- "Không tìm thấy" if no results | Page loaded |
| PROD03 | Filter products by category | 1. Go to /marketplace<br>2. Click on category dropdown/filter<br>3. Select a category | - Products filtered by category<br>- Category name shown in filter<br>- Product count updates | Page loaded |

---

### Product Detail Page (/product/:id)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PROD04 | View product detail | 1. Go to /marketplace<br>2. Click on any product card | - Navigate to /product/{id}<br>- Main image displays<br>- Product name, price, description shown<br>- "Thêm vào giỏ hàng" button visible<br>- Vendor info section shows | Product exists |
| PROD05 | Change product quantity | 1. Open product detail page<br>2. Click "+" button to increase qty<br>3. Click "-" button to decrease qty | - Quantity updates in input<br>- Cannot go below 1<br>- Cannot exceed stock quantity | Product detail opened |
| PROD06 | View product reviews | 1. Open product detail page<br>2. Scroll to reviews section | - Reviews section shows<br>- Average rating displayed<br>- Individual reviews with: avatar, name, date, rating stars, comment<br>- "Chưa có đánh giá" if empty | Product detail opened |
