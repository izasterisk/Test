# Feature_Product - Product UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Product |
| **Test requirement** | Marketplace and Product Detail pages available |
| **Number of TCs** | 14 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 14 | 0 |
| Round 2 | 0 | 0 | 14 | 0 |
| Round 3 | 0 | 0 | 14 | 0 |

---

## Test Cases

### Marketplace Page (/marketplace)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PROD01 | View product listing - initial load | 1. Open /marketplace page | - Loading spinner shows first<br>- Product grid displays<br>- Each card: image, name, price, rating<br>- Pagination visible | Page loaded |
| PROD02 | Search product by name - found | 1. Go to /marketplace<br>2. Enter "thuốc trừ sâu" in search<br>3. Press Enter | - Loading shows<br>- Results filtered by keyword<br>- Matching products displayed<br>- Search term highlighted (if any) | Products exist |
| PROD03 | Search product - no results | 1. Go to /marketplace<br>2. Enter "xyznotexist123"<br>3. Press Enter | - "Không tìm thấy sản phẩm" message<br>- Empty state illustration<br>- Clear search suggestion | Page loaded |
| PROD04 | Search product - empty query | 1. Go to /marketplace<br>2. Clear search box<br>3. Press Enter | - All products shown<br>- Filter reset | Page loaded |
| PROD05 | Filter by category | 1. Go to /marketplace<br>2. Click category dropdown<br>3. Select "Phân bón" | - Products filtered by category<br>- Category name shown as active filter<br>- Product count updates | Categories exist |
| PROD06 | Clear filter | 1. Apply category filter<br>2. Click "Xóa bộ lọc" or X button | - All products shown again<br>- Filter cleared<br>- Dropdown reset | Filter applied |
| PROD07 | Pagination - next page | 1. Go to /marketplace (many products)<br>2. Click page 2 or "Sau" | - Page 2 products load<br>- Scroll to top<br>- Page 2 highlighted<br>- URL updates (if applicable) | Multiple pages |
| PROD08 | Pagination - previous page | 1. Go to page 2<br>2. Click "Trước" or page 1 | - Page 1 products load<br>- Page 1 highlighted | On page 2+ |

---

### Product Detail Page (/product/:id)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PROD09 | View product detail - all info | 1. Go to /marketplace<br>2. Click on any product card | - Navigate to /product/{id}<br>- Main image displays<br>- Name, price, description shown<br>- Stock quantity shown<br>- Vendor info visible<br>- Reviews section visible | Product exists |
| PROD10 | Product image gallery | 1. Open product detail<br>2. Click on thumbnail images | - Main image changes<br>- Thumbnail highlighted<br>- Smooth transition | Product has multiple images |
| PROD11 | Increase quantity | 1. Open product detail (stock = 10)<br>2. Click "+" button 3 times | - Quantity shows 4<br>- Each click increments by 1 | Stock > 1 |
| PROD12 | Decrease quantity | 1. Open product detail<br>2. Set quantity to 5<br>3. Click "-" button 2 times | - Quantity shows 3<br>- Cannot go below 1 | Quantity > 1 |
| PROD13 | Quantity max limit | 1. Open product detail (stock = 5)<br>2. Try to increase quantity beyond 5 | - Quantity stops at 5<br>- "+" button disabled or no effect<br>- Cannot exceed stock | Stock limited |
| PROD14 | View product reviews | 1. Open product detail<br>2. Scroll to reviews section | - Average rating with stars<br>- Review count shown<br>- Individual reviews: avatar, name, date, rating, comment<br>- "Chưa có đánh giá" if empty | Product detail opened |
