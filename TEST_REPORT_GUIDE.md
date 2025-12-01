# Test Report Guide - VerdantTech Solutions Backend

## Overview

This document provides guidance for writing Test Reports for VerdantTech Solutions Backend (.NET 8).

---

## Tab: Test Cases (Function List)

### Test Cases Tab Structure

| No | Function Name | Sheet Name | Description | Pre-Condition |
|----|---------------|------------|-------------|---------------|

---

## Function Name and Sheet Name List

### Total: **15 Features** (15 detail sheets)

| No | Function Name | Sheet Name | Description | Pre-Condition |
|----|---------------|------------|-------------|---------------|
| 1 | Authentication | Feature_Auth | Login, register, forgot password, refresh token | Test account available |
| 2 | User Management | Feature_User | Manage user info and addresses | Logged in |
| 3 | Product | Feature_Product | Manage products, categories, reviews | Logged in |
| 4 | Cart & Order | Feature_Order | Shopping cart and order placement | Logged in as Customer |
| 5 | Inventory | Feature_Inventory | Batch import, export, serial management | Product exists |
| 6 | Vendor | Feature_Vendor | Vendor registration, profile, certificates | No login required for registration |
| 7 | Payment & Wallet | Feature_Payment | PayOS payment, wallet, withdrawal | Order exists / Logged in as Vendor |
| 8 | Farm & Crop | Feature_Farm | Farm profile, crops, CO2, weather | Logged in |
| 9 | Forum | Feature_Forum | Categories, posts, comments | Logged in |
| 10 | Notification | Feature_Notification | System notifications | Logged in |
| 11 | Request & Support | Feature_Request | Support requests, refunds | Logged in |
| 12 | Chatbot | Feature_Chatbot | AI chatbot support | Logged in |
| 13 | Dashboard | Feature_Dashboard | Statistics for Admin/Staff | Logged in as Admin/Staff |
| 14 | Product Registration | Feature_ProductReg | Vendor registers new products | Logged in as Vendor |
| 15 | Certificate | Feature_Certificate | Product and vendor certificates | Product/vendor exists |

---

## Test Cases Count per Feature

| No | Feature | Test Cases |
|----|---------|------------|
| 1 | Authentication | 7 |
| 2 | User Management | 6 |
| 3 | Product | 6 |
| 4 | Cart & Order | 7 |
| 5 | Inventory | 6 |
| 6 | Vendor | 6 |
| 7 | Payment & Wallet | 6 |
| 8 | Farm & Crop | 5 |
| 9 | Forum | 6 |
| 10 | Notification | 5 |
| 11 | Request & Support | 5 |
| 12 | Chatbot | 5 |
| 13 | Dashboard | 5 |
| 14 | Product Registration | 6 |
| 15 | Certificate | 5 |

**Total: ~86 Test Cases**

---

## How to Fill Test Cases Tab

### Step 1: Fill header information
- **Project Name**: VerdantTech Solutions Backend
- **Project Code**: VTS-BE
- **Test Environment Setup Description**:
  ```
  1. Server: .NET 8 Runtime
  2. Database: MySQL 8.x
  3. Web Browser: Chrome/Edge (for Swagger)
  4. Tools: Postman, Swagger UI
  5. Test Account: admin@gmail.com / 123456
  ```

### Step 2: Fill Function List table
Copy the 15 features table above into the Test Cases tab.

### Step 3: Create Feature sheets
Create 15 sheets with names from the "Sheet Name" column above.

---

## Feature Sheet Structure

### Header for each sheet:
| Field | Value |
|-------|-------|
| Feature | [Feature Name] |
| Test requirement | [Test requirement description] |
| Number of TCs | [5-7] |

### Testing Round table:
| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | [TC count] | 0 |
| Round 2 | 0 | 0 | [TC count] | 0 |
| Round 3 | 0 | 0 | [TC count] | 0 |

### Test Cases table:
| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions | Round 1 | Test date | Tester |
|--------------|----------------------|---------------------|------------------|----------------|---------|-----------|--------|

---

## Test Case ID Naming Convention

Format: `[Feature Code]_[Number]`

| Feature | Code | Example |
|---------|------|---------|
| Authentication | AUTH | AUTH_001 - AUTH_007 |
| User Management | USER | USER_001 - USER_006 |
| Product | PROD | PROD_001 - PROD_006 |
| Cart & Order | ORD | ORD_001 - ORD_007 |
| Inventory | INV | INV_001 - INV_006 |
| Vendor | VEND | VEND_001 - VEND_006 |
| Payment & Wallet | PAY | PAY_001 - PAY_006 |
| Farm & Crop | FARM | FARM_001 - FARM_005 |
| Forum | FORUM | FORUM_001 - FORUM_006 |
| Notification | NOTI | NOTI_001 - NOTI_005 |
| Request & Support | REQ | REQ_001 - REQ_005 |
| Chatbot | CHAT | CHAT_001 - CHAT_005 |
| Dashboard | DASH | DASH_001 - DASH_005 |
| Product Registration | PREG | PREG_001 - PREG_006 |
| Certificate | CERT | CERT_001 - CERT_005 |

---

## Test Case Selection Principles (5-7 TC/feature)

Select the most important test types for each feature:

1. **Happy Path** (1-2 TC) - Test main success flow
2. **Validation** (1-2 TC) - Test invalid data  
3. **Auth/Permission** (1 TC) - Test access control
4. **Not Found** (1 TC) - Test non-existent ID
5. **Business Logic** (1 TC) - Test business constraints

---

## Next Steps

After completing the Test Cases tab, let me know to create detailed 5-7 test cases for each Feature.

**Priority order:**
1. ⭐ Authentication
2. ⭐ User Management  
3. ⭐ Product
4. ⭐ Cart & Order
5. Remaining features

---

## Notes

- Total sheets: **18 sheets**
  - 1 Cover sheet
  - 1 Test Cases sheet (list)
  - 1 Test Statistics sheet
  - 15 Feature sheets
  
- Total Test Cases: **~86 test cases**
