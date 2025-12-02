# Feature_Payment - Payment & Wallet Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Payment & Wallet |
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

### PayOS Payment

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PAY01 | Create payment link | 1. Login as Customer<br>2. Call POST `/api/PayOS/create/{orderId}`<br>3. Send return/cancel URLs | - Payment link created<br>- QR code generated<br>- Status 201 Created | Order exists (Pending) |
| PAY02 | Create payment for non-existent order | 1. Call POST `/api/PayOS/create/99999` | - Error: Order not found<br>- Status 404 Not Found | None |
| PAY03 | Get payment info | 1. Login<br>2. Call GET `/api/PayOS/payment-info/{transactionId}` | - Payment details returned<br>- Status 200 OK | Transaction exists |
| PAY04 | PayOS webhook - payment success | 1. PayOS sends webhook with success status<br>2. System processes webhook | - Order status = Paid<br>- Transaction recorded<br>- Response 200 OK | Payment completed |
| PAY05 | PayOS webhook - payment cancelled | 1. PayOS sends webhook with cancelled status<br>2. System processes webhook | - Order remains Pending<br>- Response 200 OK | Payment cancelled |

---

### Wallet

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PAY06 | Get wallet credits | 1. Login as Vendor<br>2. Call POST `/api/Wallet/{userId}/process-credits` | - Wallet balance updated<br>- Credits from delivered orders (>7 days) | Delivered orders exist |
| PAY07 | Create cashout request | 1. Login as Vendor<br>2. Call POST `/api/Wallet/cashout-request`<br>3. Send amount and bank account | - Cashout request created (Pending)<br>- Status 201 Created | Wallet has balance |
| PAY08 | Create duplicate cashout (not allowed) | 1. Login as Vendor with pending request<br>2. Call POST `/api/Wallet/cashout-request` | - Error: Already has pending request<br>- Status 400 Bad Request | Pending request exists |
| PAY09 | Get pending cashout request | 1. Login as Vendor<br>2. Call GET `/api/Wallet/{userId}/cashout-request` | - Pending request returned | Pending request exists |
| PAY10 | Delete pending cashout request | 1. Login as Vendor<br>2. Call DELETE `/api/Wallet/cashout-request` | - Request deleted<br>- Status 200 OK | Pending request exists |

---

### Cashout Processing

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PAY11 | Get all cashout requests (Admin/Staff) | 1. Login as Admin/Staff<br>2. Call GET `/api/Wallet/cashout-requests?page=1` | - List of all pending requests | Logged in as Admin/Staff |
| PAY12 | Process cashout manually - Completed | 1. Login as Admin/Staff<br>2. Call POST `/api/Wallet/{userId}/process-cashout-manual`<br>3. Send status=Completed with gatewayPaymentId | - Cashout completed<br>- Wallet balance deducted | Pending request exists |
| PAY13 | Process cashout manually - Failed | 1. Login as Admin/Staff<br>2. Call POST `/api/Wallet/{userId}/process-cashout-manual`<br>3. Send status=Failed with cancelReason | - Cashout failed<br>- Balance restored | Pending request exists |
| PAY14 | Process cashout via PayOS | 1. Login as Admin/Staff<br>2. Call POST `/api/Wallet/{userId}/process-cashout` | - PayOS transfer initiated<br>- Status updated | Pending request exists |
| PAY15 | Cashout amount exceeds balance | 1. Login as Vendor<br>2. Request cashout > wallet balance | - Error: Insufficient balance<br>- Status 400 Bad Request | Wallet with low balance |
| PAY16 | Get vendor's cashout history | 1. Login as Vendor<br>2. Call GET `/api/Wallet/{userId}/cashout-requests` | - List of vendor's cashout requests | Vendor has cashout history |
