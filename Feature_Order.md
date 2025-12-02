# Feature_Order - Cart & Order Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Cart & Order |
| **Test requirement** | API and design are available |
| **Number of TCs** | 18 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 18 | 0 |
| Round 2 | 0 | 0 | 18 | 0 |
| Round 3 | 0 | 0 | 18 | 0 |

---

## Test Cases

### Shopping Cart

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD01 | Add product to cart | 1. Login as Customer<br>2. Call POST `/api/Cart/add`<br>3. Send productId and quantity | - Product added to cart<br>- Cart total updated<br>- Status 201 Created | Logged in, product exists |
| ORD02 | Add product with insufficient stock | 1. Login as Customer<br>2. Call POST `/api/Cart/add`<br>3. Send quantity > available stock | - Error message displayed<br>- Status 400 Bad Request | Product with low stock |
| ORD03 | Update cart item quantity | 1. Login as Customer<br>2. Call PUT `/api/Cart/update`<br>3. Send new quantity | - Quantity updated<br>- Cart total recalculated<br>- Status 200 OK | Item in cart |
| ORD04 | Remove item from cart (quantity=0) | 1. Login as Customer<br>2. Call PUT `/api/Cart/update`<br>3. Send quantity = 0 | - Item removed from cart<br>- Status 200 OK | Item in cart |
| ORD05 | Get user cart | 1. Login as Customer<br>2. Call GET `/api/Cart` | - Cart items displayed<br>- Total price calculated<br>- Status 200 OK | Logged in |
| ORD06 | Get empty cart | 1. Login as new Customer<br>2. Call GET `/api/Cart` | - Empty cart message<br>- cartItems = []<br>- Status 200 OK | Logged in, no items |

---

### Order Creation

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD07 | Create order preview | 1. Login as Customer<br>2. Call POST `/api/Order/preview`<br>3. Send cart items and shipping address | - Preview created with shipping options<br>- Shipping fee calculated<br>- Status 201 Created | Items in cart, valid address |
| ORD08 | Create order from preview | 1. Have valid order preview<br>2. Call POST `/api/Order/{orderPreviewId}`<br>3. Select shipping service | - Order created with status Pending<br>- Status 201 Created | Valid preview exists |
| ORD09 | Create order with invalid preview | 1. Call POST `/api/Order/{invalidGuid}`<br>2. Send order data | - Error: Preview not found<br>- Status 404 Not Found | None |

---

### Order Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD10 | Get order by ID | 1. Login<br>2. Call GET `/api/Order/{orderId}` | - Order details returned<br>- Includes items, status, shipping<br>- Status 200 OK | Order exists |
| ORD11 | Get all orders (Admin/Staff) | 1. Login as Admin/Staff<br>2. Call GET `/api/Order?page=1&pageSize=10` | - List of all orders<br>- Pagination info<br>- Status 200 OK | Logged in as Admin/Staff |
| ORD12 | Get orders by status filter | 1. Login as Admin/Staff<br>2. Call GET `/api/Order?status=Pending` | - Only Pending orders returned | Orders exist |
| ORD13 | Get user's orders | 1. Login as Customer<br>2. Call GET `/api/Order/user/{userId}` | - Only user's orders returned | User has orders |

---

### Order Processing

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| ORD14 | Ship order (assign serials) | 1. Login as Admin/Staff<br>2. Call POST `/api/Order/{orderId}/ship`<br>3. Send serial/batch numbers | - Order status = Shipped<br>- Serials assigned<br>- Status 200 OK | Order status = Paid |
| ORD15 | Update order status to Delivered | 1. Login as Admin/Staff<br>2. Call PUT `/api/Order/{orderId}`<br>3. Send status = Delivered | - Order status updated<br>- Status 200 OK | Order status = Shipped |
| ORD16 | Cancel order (by Customer) | 1. Login as Customer<br>2. Call PUT `/api/Order/{orderId}`<br>3. Send status = Cancelled with reason | - Order cancelled<br>- Status 200 OK | Order status = Pending |
| ORD17 | Cancel paid order (not allowed) | 1. Login as Customer<br>2. Call PUT `/api/Order/{orderId}` on Paid order<br>3. Send status = Cancelled | - Error: Cannot cancel paid order<br>- Status 400 Bad Request | Order status = Paid |
| ORD18 | Process refund | 1. Login as Admin/Staff<br>2. Call PUT `/api/Order/{orderId}`<br>3. Send status = Refunded | - Order refunded<br>- Status 200 OK | Order eligible for refund |
