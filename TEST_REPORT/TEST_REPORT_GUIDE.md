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
| 1 | Authentication | 18 |
| 2 | User Management | 12 |
| 3 | Product | 12 |
| 4 | Cart & Order | 12 |
| 5 | Inventory | 14 |
| 6 | Vendor | 16 |
| 7 | Payment & Wallet | 15 |
| 8 | Farm & Crop | 14 |
| 9 | Forum | 16 |
| 10 | Notification | 12 |
| 11 | Request & Support | 12 |
| 12 | Chatbot | 12 |
| 13 | Dashboard | 14 |
| 14 | Product Registration | 14 |
| 15 | Certificate | 12 |

**Total: ~195 Test Cases**

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

Format: `TC_[Feature Code]_[Number]`

| Feature | Code | Example |
|---------|------|---------|
| Authentication | AUTH | TC_AUTH_001 - TC_AUTH_018 |
| User Management | USER | TC_USER_001 - TC_USER_012 |
| Product | PROD | TC_PROD_001 - TC_PROD_012 |
| Cart & Order | ORD | TC_ORD_001 - TC_ORD_012 |
| Inventory | INV | TC_INV_001 - TC_INV_014 |
| Vendor | VEND | TC_VEN_001 - TC_VEN_016 |
| Payment & Wallet | PAY | TC_PAY_001 - TC_PAY_015 |
| Farm & Crop | FARM | TC_FARM_001 - TC_FARM_014 |
| Forum | FORUM | TC_FOR_001 - TC_FOR_016 |
| Notification | NTF | TC_NTF_001 - TC_NTF_012 |
| Request & Support | REQ | TC_REQ_001 - TC_REQ_012 |
| Chatbot | CHAT | TC_CHAT_001 - TC_CHAT_012 |
| Dashboard | DASH | TC_DASH_001 - TC_DASH_014 |
| Product Registration | PREG | TC_PREG_001 - TC_PREG_014 |
| Certificate | CERT | TC_CERT_001 - TC_CERT_012 |

---

## UI Test Case Selection Principles (8-20 TC/feature)

Select comprehensive UI test types for each feature:

1. **Happy Path** (2-4 TC) - Test main success flows on UI
2. **Validation** (2-4 TC) - Test invalid input, error messages, boundary values
3. **Edge Cases** (1-2 TC) - Empty state, max limits, special characters
4. **Navigation** (1-2 TC) - Page routing, redirects, breadcrumbs
5. **Visual Feedback** (1-2 TC) - Loading states, success/error toasts
6. **CRUD Operations** (2-4 TC) - Create, Read, Update, Delete flows
7. **Permission/Access** (1-2 TC) - Role-based access, unauthorized attempts
8. **Pagination/Filter** (1-2 TC) - List filtering, sorting, pagination

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
  
- Total Test Cases: **~195 test cases**

- Focus on **user-facing interactions** not API calls
- Test both **success** and **error** scenarios on UI
- Include **visual feedback** (loading, toast messages)
- Each feature has **8-20 detailed test cases**
