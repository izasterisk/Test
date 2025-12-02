# Feature_Payment - Payment & Wallet UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Payment & Wallet |
| **Test requirement** | Wallet, Transactions, Cashout pages available |
| **Number of TCs** | 15 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 15 | 0 |
| Round 2 | 0 | 0 | 15 | 0 |
| Round 3 | 0 | 0 | 15 | 0 |

---

## Test Cases

### Wallet Overview

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PAY01 | View wallet page | 1. Login as Vendor<br>2. Navigate to Wallet/Ví tiền | - Balance card displays<br>- Balance formatted as VND<br>- Quick actions: Nạp tiền, Rút tiền, Lịch sử<br>- Recent transactions shown | Logged in as Vendor |
| PAY02 | Wallet balance card display | 1. On wallet page<br>2. Observe balance card | - Balance card has distinct styling<br>- Currency symbol (₫) displayed<br>- Large readable amount<br>- Card responsive on mobile | Wallet page open |

---

### Transaction History

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PAY03 | View transaction history | 1. On wallet page<br>2. Click "Lịch sử giao dịch" | - Transaction list displays<br>- Each row: Date, Type, Amount, Status<br>- Credits in green (+)<br>- Debits in red (-) | Has transactions |
| PAY04 | Filter transactions by type | 1. On transaction history<br>2. Click type filter<br>3. Select "Rút tiền" | - Filter shows: Tất cả, Nạp, Rút, Mua hàng, Hoàn tiền<br>- Table shows selected type only<br>- Clear filter available | Transactions exist |
| PAY05 | Filter by date range | 1. On transaction history<br>2. Select "30 ngày gần đây" | - Date presets available<br>- Custom range option<br>- Results filtered by date | Transactions exist |
| PAY06 | View transaction detail | 1. On transaction list<br>2. Click a transaction row | - Detail modal opens<br>- Shows: ID, Timestamp, Amount, Fee<br>- Reference/Order ID if applicable<br>- Status badge | Transactions exist |

---

### Cashout/Withdrawal

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PAY07 | Open cashout form | 1. On wallet page<br>2. Click "Rút tiền" button | - Cashout form opens<br>- Available balance shown<br>- Amount input field<br>- Bank account selection<br>- Submit button | Has positive balance |
| PAY08 | Cashout - valid amount | 1. Open cashout form<br>2. Enter amount: 500,000<br>3. Select bank account<br>4. Click "Yêu cầu rút tiền" | - Confirmation dialog shows<br>- After confirm: "Yêu cầu đã được gửi"<br>- Pending balance updated | Balance ≥ 500,000 |
| PAY09 | Cashout - exceeds balance | 1. Open cashout form (balance: 100,000)<br>2. Enter amount: 500,000<br>3. Try submit | - Error "Số tiền vượt quá số dư khả dụng"<br>- Available balance shown<br>- Form not submitted | Balance < requested |
| PAY10 | Cashout - below minimum | 1. Open cashout form<br>2. Enter amount: 10,000<br>3. Try submit | - Error "Số tiền rút tối thiểu là 50,000 VND"<br>- Minimum amount info shown<br>- Form not submitted | Amount < minimum |
| PAY11 | Cashout - no bank account | 1. User has no bank account linked<br>2. Click "Rút tiền" | - Message "Vui lòng thêm tài khoản ngân hàng"<br>- "Thêm tài khoản" button shown<br>- Cannot proceed | No bank linked |

---

### Bank Account Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PAY12 | View add bank form | 1. Navigate to bank account settings<br>2. Click "Thêm tài khoản" | - Form shows: Bank dropdown, Account Number, Holder Name<br>- Bank list has common banks<br>- Required fields marked | Logged in |
| PAY13 | Add bank account - valid | 1. Open add bank form<br>2. Select Bank: "Vietcombank"<br>3. Enter Account: "1234567890123"<br>4. Enter Holder: "NGUYEN VAN A"<br>5. Click "Lưu" | - Form validates<br>- Success "Thêm tài khoản thành công"<br>- Account in list<br>- Can use for cashout | Form open |
| PAY14 | Add bank - invalid account | 1. Open add bank form<br>2. Select bank<br>3. Enter Account: "123" (too short)<br>4. Try submit | - Error "Số tài khoản không hợp lệ"<br>- Format hint shown<br>- Form not submitted | Form open |
| PAY15 | Delete bank account | 1. On bank account list<br>2. Click delete icon<br>3. Confirm deletion | - Confirmation dialog "Xác nhận xóa tài khoản?"<br>- After confirm: Account removed<br>- Toast "Đã xóa tài khoản" | Has bank account |
