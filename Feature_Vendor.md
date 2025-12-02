# Feature_Vendor - Vendor UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Vendor |
| **Test requirement** | Vendor registration, Vendor dashboard available |
| **Number of TCs** | 6 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 6 | 0 |
| Round 2 | 0 | 0 | 6 | 0 |
| Round 3 | 0 | 0 | 6 | 0 |

---

## Test Cases

### Vendor Registration (/signup - Vendor tab)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| VEND01 | Register as vendor | 1. Go to /signup page<br>2. Click "Đăng ký làm Vendor" tab<br>3. Fill vendor registration form:<br>- Business name<br>- Tax ID<br>- Address<br>- Contact info<br>4. Click "Đăng ký" | - Form validates all fields<br>- Loading spinner shows<br>- Success message shows<br>- Pending approval status | Page loaded |
| VEND02 | Register with missing required fields | 1. Go to /signup vendor tab<br>2. Leave Business name empty<br>3. Click "Đăng ký" | - Validation error shows<br>- "Tên doanh nghiệp không được để trống"<br>- Form not submitted | Page loaded |

---

### Vendor Dashboard (/vendor)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| VEND03 | View vendor dashboard | 1. Login as approved Vendor<br>2. Auto-redirect to /vendor dashboard | - Dashboard loads<br>- Stats cards show: Revenue, Products, Orders, Rating<br>- Recent activity list<br>- Sidebar menu visible | Logged in as Vendor |
| VEND04 | Navigate vendor sidebar | 1. On Vendor dashboard<br>2. Click "Sản phẩm" in sidebar<br>3. Click "Đơn hàng" in sidebar<br>4. Click "Ví tiền" in sidebar | - Each menu item navigates correctly<br>- Active menu highlighted<br>- Page content changes | Logged in as Vendor |
| VEND05 | Vendor logout | 1. On Vendor dashboard<br>2. Click "Đăng xuất" button in header | - Confirmation (if any)<br>- Redirect to /login<br>- Session cleared | Logged in as Vendor |
| VEND06 | View vendor profile | 1. On Vendor dashboard<br>2. Click on "Thông tin" or profile menu | - Vendor info page loads<br>- Business details shown<br>- Edit button available | Logged in as Vendor |
