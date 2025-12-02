# Feature_Order - Cart & Order UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Cart & Order |
| **Test requirement** | Cart, Preview Order, Order History pages available |
| **Number of TCs** | 12 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 12 | 0 |
| Round 2 | 0 | 0 | 12 | 0 |
| Round 3 | 0 | 0 | 12 | 0 |

---

## Test Cases

### Cart Page (/cart)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD01 | View cart page | 1. Login as customer<br>2. Click cart icon in navbar<br>3. Navigate to /cart | - Cart page displays<br>- Item list with images, names, prices<br>- Quantity controls per item<br>- Total amount calculated | Logged in, has items in cart |
| ORD02 | View empty cart | 1. Login with empty cart<br>2. Navigate to /cart | - "Giỏ hàng trống" message<br>- Empty state illustration<br>- "Tiếp tục mua sắm" button<br>- Links to marketplace | Logged in, empty cart |
| ORD03 | Increase item quantity | 1. Open /cart<br>2. Click "+" on an item<br>3. Observe changes | - Quantity increases by 1<br>- Item subtotal updates<br>- Cart total updates<br>- "+" disabled at max stock | Cart has items |
| ORD04 | Decrease item quantity | 1. Open /cart<br>2. Click "-" on item with qty > 1 | - Quantity decreases by 1<br>- Subtotal updates<br>- Cart total updates | Item qty > 1 |
| ORD05 | Remove item from cart | 1. Open /cart<br>2. Click remove/trash icon on item<br>3. Confirm if prompted | - Item removed from list<br>- Cart total updates<br>- Success toast shown<br>- Empty state if last item | Cart has items |
| ORD06 | Select/Deselect items | 1. Open /cart<br>2. Uncheck one item checkbox<br>3. Observe total | - Item unchecked<br>- Total recalculates without item<br>- "Select all" checkbox updates | Multiple items in cart |

---

### Preview Order / Checkout

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD07 | Proceed to checkout | 1. Open /cart with items<br>2. Select items<br>3. Click "Thanh toán" button | - Navigate to preview order page<br>- Selected items shown<br>- Address selection visible<br>- Payment method options | Items selected in cart |
| ORD08 | Select shipping address | 1. On preview order page<br>2. Click "Thay đổi" on address<br>3. Select different address | - Address selection modal opens<br>- Addresses listed<br>- Selected address updates<br>- Shipping fee may update | Has multiple addresses |
| ORD09 | Apply voucher code | 1. On preview order page<br>2. Enter voucher: "DISCOUNT10"<br>3. Click "Áp dụng" | - Voucher applied<br>- Discount shown<br>- Total recalculated<br>- Success message | Valid voucher exists |
| ORD10 | Apply invalid voucher | 1. On preview order page<br>2. Enter voucher: "INVALID123"<br>3. Click "Áp dụng" | - Error "Mã giảm giá không hợp lệ"<br>- No discount applied<br>- Total unchanged | Preview order page |
| ORD11 | Place order successfully | 1. On preview order<br>2. Select address<br>3. Select payment: COD<br>4. Click "Đặt hàng" | - Loading shows<br>- Success page displays<br>- Order ID shown<br>- Redirect to order history | All required info filled |
| ORD12 | Place order - no address | 1. On preview order<br>2. No address selected<br>3. Click "Đặt hàng" | - Error "Vui lòng chọn địa chỉ giao hàng"<br>- Order not placed<br>- Address field highlighted | No address selected |
