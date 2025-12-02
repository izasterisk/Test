# Feature 7: Payment & Wallet - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_Payment |
| **Feature** | Payment & Wallet Management |
| **Module** | Wallet, Transactions, Cashout |
| **Total Test Cases** | 15 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 7.1 Wallet Overview

| TC ID | TC_PAY_001 |
|-------|------------|
| **Description** | Verify Wallet page displays correctly |
| **Pre-conditions** | User logged in with wallet enabled |
| **Procedure** | 1. Navigate to Wallet/Payment section<br>2. Observe wallet overview page |
| **Expected Results** | - Current balance displayed prominently<br>- Balance formatted as currency (VND)<br>- Quick action buttons: Top Up, Withdraw, History<br>- Recent transactions section visible |

| TC ID | TC_PAY_002 |
|-------|------------|
| **Description** | Verify wallet balance card styling |
| **Pre-conditions** | User on Wallet page |
| **Procedure** | 1. Observe the balance card component<br>2. Check visual elements |
| **Expected Results** | - Balance card has distinct styling<br>- Currency symbol displayed correctly<br>- Large readable font for amount<br>- Card responsive on mobile |

### 7.2 Transaction History

| TC ID | TC_PAY_003 |
|-------|------------|
| **Description** | Verify transaction history list |
| **Pre-conditions** | User has transaction history |
| **Procedure** | 1. Click "Transaction History" or scroll to history section<br>2. Observe transaction list |
| **Expected Results** | - List shows all transactions<br>- Each row: Date, Type, Amount, Status, Description<br>- Credits shown in green (+)<br>- Debits shown in red (-)<br>- Pagination if many records |

| TC ID | TC_PAY_004 |
|-------|------------|
| **Description** | Verify transaction filter by type |
| **Pre-conditions** | User on transaction history page |
| **Procedure** | 1. Click filter dropdown<br>2. Select "Withdrawals" only<br>3. Observe filtered results |
| **Expected Results** | - Filter dropdown shows: All, Deposits, Withdrawals, Purchases, Refunds<br>- Table shows only selected type<br>- Clear filter button available<br>- Count updates with filter |

| TC ID | TC_PAY_005 |
|-------|------------|
| **Description** | Verify transaction date range filter |
| **Pre-conditions** | User on transaction history page |
| **Procedure** | 1. Click date range selector<br>2. Select "Last 30 days"<br>3. Observe filtered results |
| **Expected Results** | - Date picker/presets available<br>- Options: Today, Last 7 days, Last 30 days, Custom<br>- Custom allows start/end date selection<br>- Results filtered by date range |

| TC ID | TC_PAY_006 |
|-------|------------|
| **Description** | Verify transaction detail view |
| **Pre-conditions** | User has transactions |
| **Procedure** | 1. Click on a transaction row<br>2. Observe detail view |
| **Expected Results** | - Modal or expandable section opens<br>- Shows: Transaction ID, Timestamp, Amount, Fee (if any)<br>- Reference/Order ID if applicable<br>- Status with colored badge |

### 7.3 Cashout/Withdrawal Request

| TC ID | TC_PAY_007 |
|-------|------------|
| **Description** | Verify cashout request form display |
| **Pre-conditions** | User has positive wallet balance |
| **Procedure** | 1. Click "Withdraw" or "Cashout" button<br>2. Observe withdrawal form |
| **Expected Results** | - Form shows available balance<br>- Amount input field<br>- Bank account selection (if linked)<br>- "Add Bank Account" option if none<br>- Submit and Cancel buttons |

| TC ID | TC_PAY_008 |
|-------|------------|
| **Description** | Verify cashout with valid amount |
| **Pre-conditions** | Balance: 1,000,000 VND, Bank account linked |
| **Procedure** | 1. Open cashout form<br>2. Enter amount: 500,000<br>3. Select bank account<br>4. Click "Request Withdrawal" |
| **Expected Results** | - Form validates amount within balance<br>- Confirmation dialog shows details<br>- After confirm: "Withdrawal request submitted"<br>- Pending balance updated |

| TC ID | TC_PAY_009 |
|-------|------------|
| **Description** | Verify cashout validation - exceeds balance |
| **Pre-conditions** | Balance: 100,000 VND |
| **Procedure** | 1. Open cashout form<br>2. Enter amount: 500,000 (exceeds balance)<br>3. Try to submit |
| **Expected Results** | - Validation error: "Amount exceeds available balance"<br>- Available balance shown for reference<br>- Form does not submit<br>- Amount field highlighted |

| TC ID | TC_PAY_010 |
|-------|------------|
| **Description** | Verify cashout validation - minimum amount |
| **Pre-conditions** | User on cashout form |
| **Procedure** | 1. Enter amount: 1,000 (below minimum)<br>2. Try to submit |
| **Expected Results** | - Validation error: "Minimum withdrawal is 50,000 VND"<br>- Minimum amount info displayed<br>- Form does not submit |

| TC ID | TC_PAY_011 |
|-------|------------|
| **Description** | Verify cashout without linked bank account |
| **Pre-conditions** | User has no bank account linked |
| **Procedure** | 1. Click "Withdraw" button<br>2. Observe the form/message |
| **Expected Results** | - Message: "Please add a bank account first"<br>- "Add Bank Account" button prominently shown<br>- Cannot proceed without bank account |

### 7.4 Bank Account Management

| TC ID | TC_PAY_012 |
|-------|------------|
| **Description** | Verify add bank account form |
| **Pre-conditions** | User navigates to bank account settings |
| **Procedure** | 1. Click "Add Bank Account"<br>2. Observe the form fields |
| **Expected Results** | - Form shows: Bank Name dropdown, Account Number, Account Holder Name<br>- Bank selection has common banks<br>- Required field indicators present<br>- Save and Cancel buttons |

| TC ID | TC_PAY_013 |
|-------|------------|
| **Description** | Verify add bank account with valid data |
| **Pre-conditions** | User on add bank account form |
| **Procedure** | 1. Select Bank: "Vietcombank"<br>2. Enter Account Number: "1234567890123"<br>3. Enter Holder Name: "NGUYEN VAN A"<br>4. Click "Save" |
| **Expected Results** | - Form validates all fields<br>- Success: "Bank account added successfully"<br>- New account appears in list<br>- Can be selected for withdrawals |

| TC ID | TC_PAY_014 |
|-------|------------|
| **Description** | Verify bank account validation - invalid account number |
| **Pre-conditions** | User on add bank account form |
| **Procedure** | 1. Select a bank<br>2. Enter Account Number: "123" (too short)<br>3. Try to submit |
| **Expected Results** | - Validation error: "Invalid account number format"<br>- Expected format hint shown<br>- Form does not submit |

| TC ID | TC_PAY_015 |
|-------|------------|
| **Description** | Verify delete bank account |
| **Pre-conditions** | User has a linked bank account |
| **Procedure** | 1. Go to bank account list<br>2. Click delete icon on an account<br>3. Confirm deletion |
| **Expected Results** | - Confirmation dialog: "Are you sure you want to remove this account?"<br>- After confirm: Account removed from list<br>- Toast: "Bank account removed"<br>- Cannot use for future withdrawals |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 15 |
| Priority - High | 7 |
| Priority - Medium | 5 |
| Priority - Low | 3 |
