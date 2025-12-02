# Feature_Order - Cart & Order UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Cart & Order |
| **Test requirement** | Cart page, Preview order, Order history pages available |
| **Number of TCs** | 16 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 16 | 0 |
| Round 2 | 0 | 0 | 16 | 0 |
| Round 3 | 0 | 0 | 16 | 0 |

---

## Test Cases

### Add to Cart (from Product Detail)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD01 | Add product to cart - success | 1. Login as customer<br>2. Go to product detail page<br>3. Set quantity = 2<br>4. Click "Thêm vào giỏ hàng" | - Loading spinner on button<br>- Success toast with "Xem giỏ hàng →" link<br>- Cart badge updates (+2) | Logged in, in stock |
| ORD02 | Add to cart - not logged in | 1. Logout<br>2. Go to product detail<br>3. Click "Thêm vào giỏ hàng" | - Error toast "Vui lòng đăng nhập"<br>- Redirect to /login after 2s | Not logged in |
| ORD03 | Add to cart - out of stock | 1. Login<br>2. Go to product with stock = 0<br>3. Check "Thêm vào giỏ hàng" button | - Button disabled or shows "Hết hàng"<br>- Cannot add to cart | Product out of stock |
| ORD04 | Add to cart - exceed stock | 1. Login<br>2. Product with stock = 3<br>3. Set quantity = 5<br>4. Click "Thêm vào giỏ hàng" | - Error message "Chỉ còn 3 sản phẩm"<br>- Not added to cart | Stock < requested |

---

### Cart Page (/cart)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD05 | View cart with items | 1. Add items to cart<br>2. Navigate to /cart | - Cart page loads<br>- Items listed with: image, name, price, quantity<br>- Subtotal per item correct<br>- Total calculated correctly | Cart has items |
| ORD06 | View empty cart | 1. Remove all cart items<br>2. View /cart | - "Giỏ hàng đang trống" message<br>- Empty cart icon<br>- "Tiếp tục mua sắm" button visible<br>- Checkout button disabled | Empty cart |
| ORD07 | Increase item quantity | 1. Go to /cart<br>2. Click "+" on an item | - Quantity increments<br>- Subtotal recalculates<br>- Total updates<br>- Loading spinner during update | Cart has items |
| ORD08 | Decrease item quantity | 1. Go to /cart (item qty = 3)<br>2. Click "-" on the item | - Quantity decrements to 2<br>- Subtotal recalculates<br>- Total updates | Item qty > 1 |
| ORD09 | Decrease to remove item | 1. Go to /cart (item qty = 1)<br>2. Click "-" on the item | - Item removed from cart<br>- Total recalculates<br>- Or confirmation dialog shows | Item qty = 1 |
| ORD10 | Remove item - trash button | 1. Go to /cart<br>2. Click trash icon on item<br>3. Confirm in dialog | - Confirmation dialog shows<br>- Item removed<br>- Total recalculates<br>- Success feedback | Cart has items |
| ORD11 | Remove item - cancel | 1. Go to /cart<br>2. Click trash icon<br>3. Click "Hủy" in dialog | - Dialog closes<br>- Item still in cart | Cart has items |

---

### Preview Order (/preview-order)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD12 | Navigate to preview order | 1. Go to /cart with items<br>2. Click "Xem trước đơn hàng" | - Navigate to /preview-order<br>- Order items listed<br>- Delivery address section<br>- Payment method section<br>- Total amount shown | Cart has items |
| ORD13 | Select delivery address | 1. On preview order page<br>2. Click address dropdown<br>3. Select an address | - Address dropdown works<br>- Selected address displayed<br>- Shipping fee may update | Has saved addresses |
| ORD14 | Add new address from order | 1. On preview order<br>2. Click "Thêm địa chỉ mới"<br>3. Fill and save address | - Address form opens<br>- New address saved<br>- New address selected | No addresses |
| ORD15 | Select payment method | 1. On preview order<br>2. Select payment method (PayOS/COD) | - Payment options visible<br>- Selected method highlighted<br>- Order button enabled | Preview order page |
| ORD16 | Preview order - no address | 1. Go to preview order (no saved address)<br>2. Try to proceed | - Warning "Vui lòng thêm địa chỉ"<br>- Cannot proceed without address | No address saved |
