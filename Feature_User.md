# Feature_User - User Management Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | User Management |
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

### Create User (Register)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER01 | Register with valid data | 1. Go to Register Screen<br>2. Input email: `newuser@gmail.com`<br>3. Input password: `123456`<br>4. Input full name: `Nguyen Van A`<br>5. Input phone: `0901234567`<br>6. Click "Đăng ký" button | - Account created successfully<br>- Verification email sent<br>- Redirect to verify email screen | None |
| USER02 | Register with existing email | 1. Go to Register Screen<br>2. Input existing email: `admin@gmail.com`<br>3. Fill other required fields<br>4. Click "Đăng ký" button | Error message: "Email đã tồn tại" | Email already registered |
| USER03 | Register with invalid email format | 1. Go to Register Screen<br>2. Input invalid email: `invalidemail`<br>3. Click "Đăng ký" button | Validation error: "Email không đúng định dạng" | None |
| USER04 | Register with invalid phone format | 1. Go to Register Screen<br>2. Input valid email and password<br>3. Input invalid phone: `123`<br>4. Click "Đăng ký" button | Validation error: "Số điện thoại không đúng định dạng Việt Nam" | None |
| USER05 | Register with missing required fields | 1. Go to Register Screen<br>2. Leave email empty<br>3. Click "Đăng ký" button | Validation error: "Email là bắt buộc" | None |

---

### Create Staff Account (Admin only)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER06 | Admin creates staff account | 1. Login as Admin<br>2. Go to Staff Management<br>3. Click "Tạo nhân viên"<br>4. Input email: `staff@gmail.com`<br>5. Input full name: `Nhan Vien A`<br>6. Click "Tạo" button | - Staff account created<br>- Auto-generated password sent to email<br>- Account is verified automatically | Logged in as Admin |
| USER07 | Non-admin tries to create staff | 1. Login as Customer/Vendor<br>2. Call API POST `/api/User/staff` | Error 403 Forbidden: "Access denied" | Logged in as non-Admin |

---

### Get User Information

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER08 | Admin/Staff gets user by ID | 1. Login as Admin/Staff<br>2. Call GET `/api/User/{id}`<br>3. Use valid user ID | - User information returned<br>- Includes: email, fullName, phone, role, status | Logged in as Admin/Staff |
| USER09 | Get user with non-existent ID | 1. Login as Admin/Staff<br>2. Call GET `/api/User/99999` | Error 404: "User not found" | Logged in as Admin/Staff |
| USER10 | Get all users with pagination | 1. Login as Admin/Staff<br>2. Call GET `/api/User?page=1&pageSize=10` | - List of users returned<br>- Pagination info included<br>- Default filter: Customer role | Logged in as Admin/Staff |
| USER11 | Get users filtered by role | 1. Login as Admin/Staff<br>2. Call GET `/api/User?role=vendor` | - Only Vendor users returned | Logged in as Admin/Staff |

---

### Update User

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER12 | Update own profile | 1. Login to account<br>2. Go to Profile Settings<br>3. Update full name: `Nguyen Van B`<br>4. Update phone: `0909876543`<br>5. Click "Lưu" button | - Profile updated successfully<br>- New info displayed | Logged in |
| USER13 | Update with invalid phone | 1. Login to account<br>2. Go to Profile Settings<br>3. Input invalid phone: `abc123`<br>4. Click "Lưu" button | Validation error: "Số điện thoại không đúng định dạng Việt Nam" | Logged in |
| USER14 | Admin updates user status | 1. Login as Admin<br>2. Go to User Management<br>3. Select a user<br>4. Change status to "Suspended"<br>5. Click "Lưu" button | - User status updated to Suspended<br>- User cannot login | Logged in as Admin |

---

### User Address Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER15 | Create new address | 1. Login to account<br>2. Go to Address Management<br>3. Click "Thêm địa chỉ"<br>4. Select Province, District, Commune<br>5. Input detail address<br>6. Click "Lưu" button | - New address created<br>- Address appears in list | Logged in |
| USER16 | Update existing address | 1. Login to account<br>2. Go to Address Management<br>3. Select an address<br>4. Update detail address<br>5. Click "Lưu" button | - Address updated successfully | Logged in, has address |
| USER17 | Get provinces list | 1. Login to account<br>2. Go to Address form<br>3. Click Province dropdown | - List of all Vietnam provinces displayed | Logged in |
| USER18 | Get districts by province | 1. Login to account<br>2. Select a province (e.g., Hồ Chí Minh)<br>3. Click District dropdown | - List of districts in selected province displayed | Logged in, province selected |

---

## API Endpoints Reference

| Endpoint | Method | Auth Required | Roles | Description |
|----------|--------|---------------|-------|-------------|
| `/api/User` | POST | No | - | Create new user (register) |
| `/api/User/staff` | POST | Yes | Admin | Create staff account |
| `/api/User/{id}` | GET | Yes | Admin, Staff | Get user by ID |
| `/api/User` | GET | Yes | Admin, Staff | Get all users with pagination |
| `/api/User/{id}` | PATCH | Yes | Any | Update user |
| `/api/User/{userId}/address` | POST | Yes | Any | Create user address |
| `/api/User/address/{addressId}` | PATCH | Yes | Any | Update user address |
| `/api/Address/provinces` | GET | Yes | Any | Get all provinces |
| `/api/Address/districts` | GET | Yes | Any | Get districts by province |
| `/api/Address/communes` | GET | Yes | Any | Get communes by district |

---

## Validation Rules

| Field | Rules |
|-------|-------|
| Email | Required, Valid format, Max 255 chars, Unique |
| Password | Required, Max 255 chars |
| FullName | Required, 2-255 chars |
| PhoneNumber | Optional, Max 20 chars, Vietnam format: `^(\+84\|84\|0)?[3-9][0-9]{8}$` |
| AvatarUrl | Optional, Max 500 chars, Valid URL format |
| Status | Enum: Active, Inactive, Suspended, Deleted |

---

## User Roles

| Role | Description |
|------|-------------|
| Customer | Default role, can browse and purchase products |
| Vendor | Can sell products, manage inventory |
| Staff | Can manage users, orders |
| Admin | Full system access |

---

## User Status

| Status | Description |
|--------|-------------|
| Active | Normal active account |
| Inactive | Account not yet activated |
| Suspended | Account temporarily blocked |
| Deleted | Soft deleted account |

---

## Response Codes

| Code | Description |
|------|-------------|
| 200 | Success |
| 201 | Created successfully |
| 400 | Bad Request - Validation error |
| 401 | Unauthorized - Not logged in |
| 403 | Forbidden - No permission |
| 404 | Not Found - User not found |
| 409 | Conflict - Email already exists |
| 500 | Internal Server Error |
