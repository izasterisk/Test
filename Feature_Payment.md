# Feature_Payment - Payment & Wallet UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Payment & Wallet |
| **Test requirement** | Wallet page, Cashout page available |
| **Number of TCs** | 5 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 5 | 0 |
| Round 2 | 0 | 0 | 5 | 0 |
| Round 3 | 0 | 0 | 5 | 0 |

---

## Test Cases

### Wallet Page (/vendor/wallet)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PAY01 | View wallet balance | 1. Login as Vendor<br>2. Navigate to Wallet page from sidebar | - Wallet page loads<br>- Current balance displayed prominently<br>- Transaction history list shows<br>- "Rút tiền" button visible | Logged in as Vendor |
| PAY02 | View transaction history | 1. Go to Wallet page<br>2. Scroll to transaction list | - Transactions listed with: date, type, amount, status<br>- Pagination if many transactions<br>- Filter by date/type (if available) | Logged in as Vendor |

---

### Cashout Request

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PAY03 | Create cashout request | 1. Go to Wallet page<br>2. Click "Rút tiền" button<br>3. Enter amount: 500000<br>4. Select bank account<br>5. Click "Xác nhận" | - Cashout form/modal opens<br>- Bank account dropdown works<br>- Amount validation (min/max)<br>- Success toast "Yêu cầu rút tiền đã được gửi"<br>- Balance updates | Balance >= 500000 |
| PAY04 | Cashout with insufficient balance | 1. Go to Wallet page (balance = 100000)<br>2. Click "Rút tiền"<br>3. Enter amount: 500000<br>4. Click "Xác nhận" | - Error message "Số dư không đủ"<br>- Request not submitted | Balance < requested amount |
| PAY05 | View cashout history | 1. Go to Cashout history page<br>2. View list of previous requests | - Cashout requests listed<br>- Status shown: Pending, Approved, Rejected<br>- Amount and date displayed | Logged in as Vendor |
