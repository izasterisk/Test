# Feature_Auth - Authentication Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Authentication |
| **Test requirement** | API and design are available |
| **Number of TCs** | 20 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 20 | 0 |
| Round 2 | 0 | 0 | 20 | 0 |
| Round 3 | 0 | 0 | 20 | 0 |

---

## Test Cases

### Login

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH01 | Login with invalid email format | 1. Go to Login Screen<br>2. Input invalid email: `exampleGmail.com`<br>3. Click on "Đăng nhập" button | A tooltip validation message displays with content "Please include an '@' in the email address" | None |
| AUTH02 | Login with invalid password (less than 6 chars) | 1. Go to Login Screen<br>2. Input valid email: `test@gmail.com`<br>3. Input invalid password: `123`<br>4. Click on "Đăng nhập" button | A validation message displays with content "Password must be at least 6 characters long" | None |
| AUTH03 | Login with wrong email/password | 1. Go to Login Screen<br>2. Input wrong email/password<br>3. Click on "Đăng nhập" button | A validation message displays with content "Email hoặc mật khẩu không hợp lệ" | None |
| AUTH04 | Login with correct email/password (Customer) | 1. Go to Login Screen<br>2. Input email: `customer@gmail.com`<br>3. Input password: `123456`<br>4. Click on "Đăng nhập" button | - Login successful<br>- Redirect to Customer homepage<br>- User info displayed correctly | Account exists with role Customer |
| AUTH05 | Login with correct email/password (Vendor) | 1. Go to Login Screen<br>2. Input email: `vendor@gmail.com`<br>3. Input password: `123456`<br>4. Click on "Đăng nhập" button | - Login successful<br>- Redirect to Vendor dashboard<br>- User info displayed correctly | Account exists with role Vendor |
| AUTH06 | Login with correct email/password (Admin) | 1. Go to Login Screen<br>2. Input email: `admin@gmail.com`<br>3. Input password: `123456`<br>4. Click on "Đăng nhập" button | - Login successful<br>- Redirect to Admin dashboard<br>- User info displayed correctly | Account exists with role Admin |

---

### Google Login

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH07 | Google login with valid Google account | 1. Go to Login Screen<br>2. Click on "Đăng nhập với Google" button<br>3. Select a valid Google account<br>4. Complete Google authentication | - Login successful<br>- Redirect to homepage<br>- User info from Google displayed | Valid Google account |
| AUTH08 | Google login with new account (first time) | 1. Go to Login Screen<br>2. Click on "Đăng nhập với Google" button<br>3. Select a new Google account (not registered) | - New account created automatically<br>- Login successful<br>- Redirect to homepage | Google account not registered in system |

---

### Send Verification Email

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH09 | Send verification to valid email | 1. Go to Register/Verify Screen<br>2. Input valid email: `newuser@gmail.com`<br>3. Click on "Gửi mã xác thực" button | - Success message displayed<br>- Email received with 8-digit verification code | Email not verified yet |
| AUTH10 | Send verification to invalid email format | 1. Go to Register/Verify Screen<br>2. Input invalid email: `invalidemail`<br>3. Click on "Gửi mã xác thực" button | Validation error: "Please provide a valid email address" | None |

---

### Verify Email

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH11 | Verify email with correct code | 1. Input email that received verification code<br>2. Input correct 8-digit code<br>3. Click on "Xác thực" button | - Success message: "Email verified successfully"<br>- Account marked as verified | Verification code sent to email |
| AUTH12 | Verify email with wrong code | 1. Input email that received verification code<br>2. Input wrong code: `00000000`<br>3. Click on "Xác thực" button | Error message: "Invalid verification code" | Verification code sent to email |
| AUTH13 | Verify email with expired code | 1. Wait for verification code to expire (>15 mins)<br>2. Input email and expired code<br>3. Click on "Xác thực" button | Error message: "Verification code has expired" | Verification code expired |

---

### Forgot Password

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH14 | Send forgot password to registered email | 1. Go to Forgot Password Screen<br>2. Input registered email: `test@gmail.com`<br>3. Click on "Gửi mã" button | - Success message displayed<br>- Email received with 8-character reset code | Account exists |
| AUTH15 | Send forgot password to unregistered email | 1. Go to Forgot Password Screen<br>2. Input unregistered email: `notexist@gmail.com`<br>3. Click on "Gửi mã" button | Error message: "Email not found" | Email not registered |

---

### Reset Password

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH16 | Reset password with valid code | 1. Input email that received reset code<br>2. Input correct 8-character code<br>3. Input new password: `newpass123`<br>4. Click on "Đặt lại mật khẩu" button | - Success message: "Password reset successfully"<br>- Can login with new password | Reset code sent to email |
| AUTH17 | Reset password with invalid new password | 1. Input email and correct code<br>2. Input short password: `123`<br>3. Click on "Đặt lại mật khẩu" button | Validation error: "Password must be at least 6 characters long" | Reset code sent to email |

---

### Change Password

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH18 | Change password with correct old password | 1. Login to account<br>2. Go to Change Password Screen<br>3. Input correct old password<br>4. Input new password: `newpass123`<br>5. Click on "Đổi mật khẩu" button | - Success message: "Password changed successfully"<br>- Can login with new password | Logged in |
| AUTH19 | Change password with wrong old password | 1. Login to account<br>2. Go to Change Password Screen<br>3. Input wrong old password<br>4. Input new password: `newpass123`<br>5. Click on "Đổi mật khẩu" button | Error message: "Old password is incorrect" | Logged in |

---

### Logout

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH20 | Logout successfully | 1. Login to account<br>2. Click on user avatar/menu<br>3. Click on "Đăng xuất" button | - Logout successful<br>- Redirect to Login screen<br>- Token removed from localStorage<br>- Cannot access protected pages | Logged in |

---

## API Endpoints Reference

| Endpoint | Method | Auth Required | Description |
|----------|--------|---------------|-------------|
| `/api/Auth/login` | POST | No | User login with email/password |
| `/api/Auth/google-login` | POST | No | Login with Google account |
| `/api/Auth/send-verification` | POST | No | Send verification email |
| `/api/Auth/verify-email` | POST | No | Verify email with code |
| `/api/Auth/refresh-token` | POST | No | Refresh JWT token |
| `/api/Auth/profile` | GET | Yes | Get current user profile |
| `/api/Auth/forgot-password` | POST | No | Send forgot password email |
| `/api/Auth/reset-password` | POST | No | Reset password with code |
| `/api/Auth/change-password` | POST | Yes | Change password |
| `/api/Auth/logout` | POST | Yes | Logout user |

---

## Request Body Examples

### Login
```json
{
  "email": "admin@gmail.com",
  "password": "123456"
}
```

### Google Login
```json
{
  "idToken": "google_id_token_here"
}
```

### Send Verification / Forgot Password
```json
{
  "email": "user@gmail.com"
}
```

### Verify Email
```json
{
  "email": "user@gmail.com",
  "code": "12345678"
}
```

### Reset Password
```json
{
  "email": "user@gmail.com",
  "code": "ABCD1234",
  "newPassword": "newpassword123"
}
```

### Change Password
```json
{
  "email": "user@gmail.com",
  "oldPassword": "currentpassword",
  "newPassword": "newpassword123"
}
```

### Refresh Token
```json
{
  "refreshToken": "refresh_token_string_here"
}
```

---

## Validation Rules

| Field | Rules |
|-------|-------|
| Email | Required, Valid email format, Max 255 chars |
| Password | Required, Min 6 chars, Max 100 chars |
| Verification Code | Required, Exactly 8 digits |
| Reset Code | Required, Exactly 8 characters |

---

## Response Codes

| Code | Description |
|------|-------------|
| 200 | Success |
| 400 | Bad Request - Validation error |
| 401 | Unauthorized - Invalid credentials or token |
| 404 | Not Found - Email not registered |
| 500 | Internal Server Error |
