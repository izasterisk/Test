# Feature_Product - Product UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Product |
| **Test requirement** | Marketplace, Product Detail pages available |
| **Number of TCs** | 12 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 12 | 0 |
| Round 2 | 0 | 0 | 12 | 0 |
| Round 3 | 0 | 0 | 12 | 0 |

---

## Test Cases

### Marketplace Page (/marketplace)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PROD01 | View marketplace page | 1. Open /marketplace<br>2. Observe page layout | - Product grid displays<br>- Search bar visible<br>- Category filter sidebar<br>- Pagination at bottom | Page loaded |
| PROD02 | Search products by name | 1. Open /marketplace<br>2. Type "rau" in search box<br>3. Press Enter or click search | - Results show matching products<br>- Search term highlighted<br>- "X kết quả" count shown | Page loaded |
| PROD03 | Search with no results | 1. Open /marketplace<br>2. Search for "xyznotexist123"<br>3. Press Enter | - "Không tìm thấy sản phẩm" message<br>- Empty state illustration<br>- Clear search suggestion | Page loaded |
| PROD04 | Filter by category | 1. Open /marketplace<br>2. Click category "Rau củ" in sidebar<br>3. Observe filtered results | - Only vegetable products shown<br>- Category chip active<br>- Product count updates | Page loaded |
| PROD05 | Filter by price range | 1. Open /marketplace<br>2. Set price min: 10000<br>3. Set price max: 50000<br>4. Click apply/filter | - Products in price range shown<br>- Filter badge shows range<br>- Clear filter option | Page loaded |
| PROD06 | Sort products by price | 1. Open /marketplace<br>2. Click sort dropdown<br>3. Select "Giá: Thấp → Cao" | - Products reorder by price ascending<br>- Sort option shown as selected | Page loaded |

---

### Product Detail Page (/product/:id)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PROD07 | View product detail page | 1. Click a product from marketplace<br>2. Navigate to /product/:id | - Product images gallery<br>- Product name, price displayed<br>- Description section<br>- Vendor info shown<br>- Quantity selector | Page loaded |
| PROD08 | Change quantity | 1. Open product detail<br>2. Click "+" to increase qty to 3<br>3. Click "-" to decrease to 2 | - Quantity updates in input<br>- "+" disabled at max stock<br>- "-" disabled at 1 | Product detail page |
| PROD09 | View product images gallery | 1. Open product detail<br>2. Click thumbnail images<br>3. Click main image to zoom | - Main image changes on thumbnail click<br>- Zoom modal opens on main click<br>- Navigation arrows in gallery | Product has multiple images |
| PROD10 | Add to cart from detail page | 1. Open product detail<br>2. Set quantity: 2<br>3. Click "Thêm vào giỏ" | - Loading on button<br>- Success toast "Đã thêm vào giỏ hàng"<br>- Cart icon count updates | Logged in |
| PROD11 | Add to cart - not logged in | 1. Logout if logged in<br>2. Open product detail<br>3. Click "Thêm vào giỏ" | - Redirect to /login<br>- Or modal prompts login<br>- Message "Vui lòng đăng nhập" | Not logged in |
| PROD12 | View product reviews | 1. Open product detail<br>2. Scroll to reviews section | - Reviews list displays<br>- Star ratings shown<br>- Reviewer name, date visible<br>- Average rating at top | Product detail page |
