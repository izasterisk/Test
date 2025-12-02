# Feature_Auth - Authentication UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Authentication |
| **Test requirement** | Login, SignUp, ForgotPassword, VerifyEmail pages available |
| **Number of TCs** | 18 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 18 | 0 |
| Round 2 | 0 | 0 | 18 | 0 |
| Round 3 | 0 | 0 | 18 | 0 |

---

## Test Cases

### Login Page (/login)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH01 | Login with valid Customer credentials | 1. Open /login page<br>2. Enter email: customer@gmail.com<br>3. Enter password: 123456<br>4. Click "Đăng nhập" button | - Loading spinner shows<br>- Redirect to homepage (/)<br>- User name shows in navbar<br>- Cart icon visible | Page loaded |
| AUTH02 | Login with valid Vendor credentials | 1. Open /login page<br>2. Enter email: vendor@gmail.com<br>3. Enter password: 123456<br>4. Click "Đăng nhập" | - Loading spinner shows<br>- Redirect to /vendor dashboard<br>- Vendor sidebar visible | Page loaded |
| AUTH03 | Login with valid Admin credentials | 1. Open /login page<br>2. Enter email: admin@gmail.com<br>3. Enter password: 123456<br>4. Click "Đăng nhập" | - Redirect to /admin dashboard<br>- Admin menu visible | Page loaded |
| AUTH04 | Login with invalid password | 1. Open /login page<br>2. Enter email: customer@gmail.com<br>3. Enter password: wrongpassword<br>4. Click "Đăng nhập" | - Error toast shows "Sai mật khẩu"<br>- Stay on login page<br>- Button returns to normal state | Page loaded |
| AUTH05 | Login with non-existent email | 1. Open /login page<br>2. Enter email: notexist@gmail.com<br>3. Enter password: 123456<br>4. Click "Đăng nhập" | - Error toast shows "Không tìm thấy tài khoản"<br>- Stay on login page | Page loaded |
| AUTH06 | Login with invalid email format | 1. Open /login page<br>2. Enter email: invalidemail (no @)<br>3. Click "Đăng nhập" | - Browser validation shows "Please include '@'"<br>- Form not submitted | Page loaded |
| AUTH07 | Login with empty email field | 1. Open /login page<br>2. Leave email empty<br>3. Enter password: 123456<br>4. Click "Đăng nhập" | - Browser shows required field validation<br>- Form not submitted | Page loaded |
| AUTH08 | Login with empty password field | 1. Open /login page<br>2. Enter email: customer@gmail.com<br>3. Leave password empty<br>4. Click "Đăng nhập" | - Browser shows required field validation<br>- Form not submitted | Page loaded |
| AUTH09 | Toggle password visibility | 1. Open /login page<br>2. Enter password: 123456<br>3. Click eye icon to show password<br>4. Click eye icon again to hide | - Password shows as plain text when visible<br>- Password shows as dots when hidden<br>- Icon changes between Eye/EyeOff | Page loaded |
| AUTH10 | Navigate to Sign Up from Login | 1. Open /login page<br>2. Click "Đăng ký ngay" link | - Navigate to /signup page<br>- Sign up form displays | Page loaded |
| AUTH11 | Navigate to Forgot Password | 1. Open /login page<br>2. Click "Quên mật khẩu?" link | - Navigate to /forgot-password page<br>- Forgot password form displays | Page loaded |

---

### Sign Up Page (/signup)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH12 | Register new customer successfully | 1. Open /signup page<br>2. Fill: Họ tên = "Test User"<br>3. Fill: Email = unique@gmail.com<br>4. Fill: SĐT = "0901234567"<br>5. Fill: Mật khẩu = "Test@123"<br>6. Fill: Xác nhận = "Test@123"<br>7. Click "Đăng ký" | - Loading spinner shows<br>- Redirect to /verify-email<br>- Success toast "Email xác thực đã được gửi" | Page loaded |
| AUTH13 | Register with password mismatch | 1. Open /signup page<br>2. Fill all fields correctly<br>3. Password = "Test@123"<br>4. Confirm = "Different123"<br>5. Click "Đăng ký" | - Error toast "Mật khẩu xác nhận không khớp"<br>- Stay on signup page<br>- Form not cleared | Page loaded |
| AUTH14 | Register with existing email | 1. Open /signup page<br>2. Fill: Email = customer@gmail.com<br>3. Fill other fields correctly<br>4. Click "Đăng ký" | - Error toast "Tài khoản này đã được sử dụng"<br>- Stay on signup page | Page loaded |
| AUTH15 | Register with invalid phone format | 1. Open /signup page<br>2. Fill: SĐT = "abc123" (invalid)<br>3. Fill other fields correctly<br>4. Click "Đăng ký" | - Validation error for phone field<br>- Form not submitted | Page loaded |

---

### Forgot Password Page (/forgot-password)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH16 | Request password reset - valid email | 1. Open /forgot-password<br>2. Enter email: customer@gmail.com<br>3. Click send button | - Loading shows<br>- Success message<br>- Redirect to /reset-password | Page loaded |
| AUTH17 | Request password reset - invalid email | 1. Open /forgot-password<br>2. Enter email: notexist@gmail.com<br>3. Click send button | - Error message "Email không tồn tại"<br>- Stay on page | Page loaded |
| AUTH18 | Back to login from forgot password | 1. Open /forgot-password<br>2. Click "Quay lại" or back button | - Navigate back to /login page | Page loaded |
