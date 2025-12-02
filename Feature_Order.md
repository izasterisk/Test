# Feature_Order - Cart & Order UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Cart & Order |
| **Test requirement** | Cart page, Preview order page available |
| **Number of TCs** | 7 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 7 | 0 |
| Round 2 | 0 | 0 | 7 | 0 |
| Round 3 | 0 | 0 | 7 | 0 |

---

## Test Cases

### Add to Cart (from Product Detail)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD01 | Add product to cart | 1. Login as customer<br>2. Go to product detail page<br>3. Set quantity = 2<br>4. Click "Thêm vào giỏ hàng" | - Loading spinner on button<br>- Success toast "Thêm vào giỏ hàng thành công!"<br>- Cart icon badge updates (+2)<br>- "Xem giỏ hàng →" link in toast | Logged in, product in stock |
| ORD02 | Add to cart without login | 1. Logout if logged in<br>2. Go to product detail page<br>3. Click "Thêm vào giỏ hàng" | - Error toast "Vui lòng đăng nhập"<br>- Redirect to /login after 2 seconds | Not logged in |

---

### Cart Page (/cart)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD03 | View cart items | 1. Login and add items to cart<br>2. Navigate to /cart | - Cart page loads<br>- Product list with: image, name, price, quantity<br>- Subtotal calculated correctly<br>- "Xem trước đơn hàng" button visible | Cart has items |
| ORD04 | Update item quantity | 1. Go to /cart<br>2. Click "+" to increase quantity<br>3. Click "-" to decrease quantity | - Quantity updates<br>- Subtotal recalculates<br>- Spinner shows during update | Cart has items |
| ORD05 | Remove item from cart | 1. Go to /cart<br>2. Click trash icon on an item<br>3. Confirm deletion in dialog | - Confirmation dialog shows<br>- Item removed from list<br>- Total recalculates<br>- "Giỏ hàng đang trống" if last item | Cart has items |

---

### Preview Order Page (/preview-order)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD06 | Preview order before checkout | 1. Go to /cart with items<br>2. Click "Xem trước đơn hàng" | - Navigate to /preview-order<br>- Order summary shows<br>- Delivery address selection<br>- Payment method options<br>- Total amount displayed | Cart has items |
| ORD07 | Empty cart state | 1. Remove all items from cart<br>2. View cart page | - "Giỏ hàng đang trống" message<br>- Empty cart icon shows<br>- "Tiếp tục mua sắm" button visible<br>- Checkout button disabled | Empty cart |
