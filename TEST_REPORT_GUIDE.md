# Test Report Guide - VerdantTech Solutions Frontend

## Overview

This document provides guidance for writing **UI Test Reports** for VerdantTech Solutions Frontend (React + Vite).
Test cases focus on **User Interface Testing** - testing user interactions, form validations, navigation, and UI behaviors.

---

## Test Environment

| Item | Value |
|------|-------|
| **Frontend** | React 18 + Vite + TypeScript |
| **UI Library** | shadcn/ui, Tailwind CSS |
| **Browser** | Chrome/Edge (latest version) |
| **Screen Resolution** | 1920x1080 (Desktop), 375x812 (Mobile) |
| **Test URL** | http://localhost:5173 |
| **Test Accounts** | Customer: customer@gmail.com / 123456<br>Vendor: vendor@gmail.com / 123456<br>Admin: admin@gmail.com / 123456 |

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
| 1 | Authentication | Feature_Auth | Login page, Sign up page, Forgot password, Email verification | Browser opened |
| 2 | User Management | Feature_User | Profile page, Edit profile, Change password, Address management | Logged in |
| 3 | Product | Feature_Product | Marketplace page, Product detail, Search, Filter, Reviews | Browser opened |
| 4 | Cart & Order | Feature_Order | Cart page, Preview order, Checkout flow, Order history | Logged in as Customer |
| 5 | Inventory | Feature_Inventory | Inventory management panel (Staff/Admin) | Logged in as Staff/Admin |
| 6 | Vendor | Feature_Vendor | Vendor registration form, Vendor dashboard, Vendor profile | Browser opened / Logged in as Vendor |
| 7 | Payment & Wallet | Feature_Payment | PayOS payment flow, Wallet page, Cashout request | Logged in as Vendor |
| 8 | Farm & Crop | Feature_Farm | Create farm page, Farm list, Farm detail, Crop management | Logged in |
| 9 | Forum | Feature_Forum | Forum page, Create post, Post detail, Comments | Logged in |
| 10 | Notification | Feature_Notification | Notification bell, Notification list, Mark as read | Logged in |
| 11 | Request & Support | Feature_Request | Ticket page, Create ticket, View ticket status | Logged in |
| 12 | Chatbot | Feature_Chatbot | Chat page, Send message, Chat history | Logged in |
| 13 | Dashboard | Feature_Dashboard | Admin dashboard, Staff dashboard, Analytics | Logged in as Admin/Staff |
| 14 | Product Registration | Feature_ProductReg | Register product page (Vendor), Product management | Logged in as Vendor |
| 15 | Certificate | Feature_Certificate | Upload certificates, View certificates, Approval status | Logged in as Vendor/Admin |

---

## Test Cases Count per Feature

| No | Feature | Test Cases |
|----|---------|------------|
| 1 | Authentication | 8 |
| 2 | User Management | 7 |
| 3 | Product | 6 |
| 4 | Cart & Order | 7 |
| 5 | Inventory | 5 |
| 6 | Vendor | 6 |
| 7 | Payment & Wallet | 5 |
| 8 | Farm & Crop | 5 |
| 9 | Forum | 6 |
| 10 | Notification | 4 |
| 11 | Request & Support | 5 |
| 12 | Chatbot | 5 |
| 13 | Dashboard | 4 |
| 14 | Product Registration | 5 |
| 15 | Certificate | 4 |

**Total: ~82 Test Cases**

---

## How to Fill Test Cases Tab

### Step 1: Fill header information
- **Project Name**: VerdantTech Solutions Frontend
- **Project Code**: VTS-FE
- **Test Environment Setup Description**:
  ```
  1. Browser: Chrome/Edge (latest)
  2. Screen: 1920x1080
  3. URL: http://localhost:5173
  4. Test Account: customer@gmail.com / 123456
  5. Tools: Chrome DevTools, Network tab
  ```

### Step 2: Fill Function List table
Copy the 15 features table above into the Test Cases tab.

### Step 3: Create Feature sheets
Create 15 sheets with names from the "Sheet Name" column above.

---

## UI Testing Types

### 1. Form Validation Testing
- Empty field submission
- Invalid data format (email, phone)
- Password mismatch
- Required field validation
- Error message display

### 2. Navigation Testing
- Page routing
- Back/Forward button
- Breadcrumb navigation
- Menu navigation

### 3. User Interaction Testing
- Button click actions
- Form input behavior
- Dropdown selection
- Modal/Dialog behavior

### 4. Visual Testing
- Loading states (spinner)
- Error states
- Success states
- Toast notifications

### 5. Responsive Testing
- Desktop layout
- Mobile layout
- Element visibility

---

## Feature Sheet Structure

### Header for each sheet:
| Field | Value |
|-------|-------|
| Feature | [Feature Name] |
| Test requirement | UI design available, Frontend deployed |
| Number of TCs | [4-8] |

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

Format: `[Feature Code][Number]`

| Feature | Code | Example |
|---------|------|---------|
| Authentication | AUTH | AUTH01 - AUTH08 |
| User Management | USER | USER01 - USER07 |
| Product | PROD | PROD01 - PROD06 |
| Cart & Order | ORD | ORD01 - ORD07 |
| Inventory | INV | INV01 - INV05 |
| Vendor | VEND | VEND01 - VEND06 |
| Payment & Wallet | PAY | PAY01 - PAY05 |
| Farm & Crop | FARM | FARM01 - FARM05 |
| Forum | FORUM | FORUM01 - FORUM06 |
| Notification | NOTI | NOTI01 - NOTI04 |
| Request & Support | REQ | REQ01 - REQ05 |
| Chatbot | CHAT | CHAT01 - CHAT05 |
| Dashboard | DASH | DASH01 - DASH04 |
| Product Registration | PREG | PREG01 - PREG05 |
| Certificate | CERT | CERT01 - CERT04 |

---

## UI Test Case Selection Principles (4-8 TC/feature)

Select the most important UI test types for each feature:

1. **Happy Path** (1-2 TC) - Test main success flow on UI
2. **Validation** (1-2 TC) - Test invalid input, error messages
3. **Edge Cases** (1 TC) - Empty state, boundary values
4. **Navigation** (1 TC) - Page routing, redirects
5. **Visual Feedback** (1 TC) - Loading, success/error messages

---

## Next Steps

After completing the Test Cases tab, see the detailed UI test cases for each Feature in corresponding files.

**Priority order:**
1. ⭐ Authentication (Login, SignUp, ForgotPassword pages)
2. ⭐ User Management (Profile page)
3. ⭐ Product (Marketplace, ProductDetail pages)
4. ⭐ Cart & Order (Cart, PreviewOrder pages)
5. Remaining features

---

## Main Pages to Test

| Page | URL | Components |
|------|-----|------------|
| Login | /login | Email input, Password input, Login button, Google login |
| Sign Up | /signup | Full name, Email, Phone, Password, Confirm password |
| Forgot Password | /forgot-password | Email input, Send button |
| Profile | /profile | Avatar, User info, Edit form, Address list |
| Marketplace | /marketplace | Product grid, Search, Filter, Pagination |
| Product Detail | /product/:id | Image gallery, Price, Quantity, Add to cart |
| Cart | /cart | Item list, Quantity controls, Remove, Total |
| Forum | /forum | Post list, Create post form, Categories |
| Chat | /chat | Message list, Input, Send button, History |
| Vendor Dashboard | /vendor | Stats cards, Activity list, Charts |

---

## Notes

- Total sheets: **18 sheets**
  - 1 Cover sheet
  - 1 Test Cases sheet (list)
  - 1 Test Statistics sheet
  - 15 Feature sheets
  
- Total Test Cases: **~82 test cases**

- Focus on **user-facing interactions** not API calls
- Test both **success** and **error** scenarios on UI
- Include **visual feedback** (loading, toast messages)
