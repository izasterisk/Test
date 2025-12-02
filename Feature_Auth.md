# Feature_Auth - Authentication UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Authentication |
| **Test requirement** | Login, SignUp, ForgotPassword pages available |
| **Number of TCs** | 8 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 8 | 0 |
| Round 2 | 0 | 0 | 8 | 0 |
| Round 3 | 0 | 0 | 8 | 0 |

---

## Test Cases

### Login Page (/login)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH01 | Login with valid credentials | 1. Open /login page<br>2. Enter email: customer@gmail.com<br>3. Enter password: 123456<br>4. Click "Đăng nhập" button | - Loading spinner shows<br>- Redirect to homepage (/)<br>- User name shows in navbar | Page loaded |
| AUTH02 | Login with invalid password | 1. Open /login page<br>2. Enter email: customer@gmail.com<br>3. Enter password: wrongpassword<br>4. Click "Đăng nhập" button | - Error toast shows "Sai mật khẩu"<br>- Stay on login page<br>- Password field stays | Page loaded |
| AUTH03 | Login with non-existent email | 1. Open /login page<br>2. Enter email: notexist@gmail.com<br>3. Enter password: 123456<br>4. Click "Đăng nhập" button | - Error toast shows "Không tìm thấy tài khoản"<br>- Stay on login page | Page loaded |
| AUTH04 | Login with empty fields | 1. Open /login page<br>2. Leave email empty<br>3. Leave password empty<br>4. Click "Đăng nhập" button | - Browser shows required field validation<br>- Form not submitted | Page loaded |

---

### Sign Up Page (/signup)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH05 | Register new customer account | 1. Open /signup page<br>2. Fill: Họ tên = "Test User"<br>3. Fill: Email = unique email<br>4. Fill: SĐT = "0901234567"<br>5. Fill: Mật khẩu = "Test@123"<br>6. Fill: Xác nhận MK = "Test@123"<br>7. Click "Đăng ký" | - Loading spinner shows<br>- Redirect to /verify-email<br>- Success toast "Email xác thực đã được gửi" | Page loaded |
| AUTH06 | Register with password mismatch | 1. Open /signup page<br>2. Fill all fields correctly<br>3. Password = "Test@123"<br>4. Confirm password = "Different123"<br>5. Click "Đăng ký" | - Error toast "Mật khẩu xác nhận không khớp"<br>- Stay on signup page | Page loaded |
| AUTH07 | Register with existing email | 1. Open /signup page<br>2. Fill: Email = customer@gmail.com (existing)<br>3. Fill other fields correctly<br>4. Click "Đăng ký" | - Error toast "Tài khoản này đã được sử dụng"<br>- Stay on signup page | Page loaded |

---

### Forgot Password Page (/forgot-password)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| AUTH08 | Request password reset | 1. Open /forgot-password page<br>2. Enter email: customer@gmail.com<br>3. Click send button | - Loading shows<br>- Success message shows<br>- Redirect to /reset-password | Page loaded |
