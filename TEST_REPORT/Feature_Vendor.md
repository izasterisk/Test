# Feature_Vendor - Vendor Management UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Vendor Management |
| **Test requirement** | Vendor Registration, Dashboard, Profile pages available |
| **Number of TCs** | 16 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 16 | 0 |
| Round 2 | 0 | 0 | 16 | 0 |
| Round 3 | 0 | 0 | 16 | 0 |

---

## Test Cases

### Vendor Registration

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| VEND01 | View vendor registration page | 1. Login as regular user<br>2. Navigate to "Trở thành người bán" | - Registration form displays<br>- Fields: Business Name, Tax ID, Description, Address<br>- Terms checkbox visible<br>- Submit button at bottom | Logged in as Customer |
| VEND02 | Register vendor - valid data | 1. Open vendor registration<br>2. Enter Business Name: "Nông Trại Xanh"<br>3. Enter Tax ID: "0123456789"<br>4. Enter description<br>5. Fill address info<br>6. Check terms agreement<br>7. Click "Đăng ký" | - Loading shows<br>- Success "Đăng ký đang chờ xét duyệt"<br>- Redirect to pending page | Registration form open |
| VEND03 | Register vendor - missing fields | 1. Open vendor registration<br>2. Leave Business Name empty<br>3. Leave Tax ID empty<br>4. Click submit | - Validation errors show<br>- "Tên doanh nghiệp là bắt buộc"<br>- "Mã số thuế là bắt buộc"<br>- Form not submitted | Registration form open |
| VEND04 | Register vendor - invalid Tax ID | 1. Open vendor registration<br>2. Fill required fields<br>3. Enter Tax ID: "abc123"<br>4. Click submit | - Validation error "Mã số thuế không hợp lệ"<br>- Format hint shown<br>- Form not submitted | Registration form open |

---

### Vendor Dashboard

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| VEND05 | View vendor dashboard | 1. Login as approved Vendor<br>2. Navigate to /vendor | - Dashboard header with business name<br>- Stats cards: Products, Orders, Revenue, Rating<br>- Recent orders section<br>- Quick action buttons | Logged in as Vendor |
| VEND06 | Vendor sidebar navigation | 1. On vendor dashboard<br>2. Observe left sidebar<br>3. Click each menu item | - Sidebar shows: Dashboard, Sản phẩm, Đơn hàng, Hồ sơ, Ví, Cài đặt<br>- Active item highlighted<br>- Navigation works correctly | Logged in as Vendor |
| VEND07 | Dashboard stats display | 1. On vendor dashboard<br>2. Observe stats cards<br>3. Click a stats card | - Numbers formatted correctly<br>- Comparison % shown (if any)<br>- Click navigates to detail | Vendor has data |
| VEND08 | Refresh dashboard data | 1. On vendor dashboard<br>2. Click refresh button<br>3. Or pull to refresh | - Loading indicator<br>- Data updates<br>- Timestamp updates | Logged in as Vendor |

---

### Vendor Profile

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| VEND09 | View vendor profile | 1. On vendor dashboard<br>2. Click "Hồ sơ" menu | - Profile displays: Business Name, Logo, Description<br>- Contact info shown<br>- Address visible<br>- Rating displayed<br>- "Chỉnh sửa" button | Logged in as Vendor |
| VEND10 | Edit vendor profile | 1. On vendor profile<br>2. Click "Chỉnh sửa"<br>3. Update description<br>4. Click "Lưu" | - Edit form opens with data<br>- Fields editable<br>- Success toast "Cập nhật thành công"<br>- Profile reflects changes | Profile page open |
| VEND11 | Upload vendor logo | 1. On vendor profile edit<br>2. Click logo area<br>3. Select valid image (PNG, < 2MB)<br>4. Save changes | - Preview shows<br>- Upload progress<br>- Logo updated on profile<br>- Success message | Edit mode active |
| VEND12 | Upload logo - invalid file | 1. On profile edit<br>2. Try upload PDF file | - Error "Chỉ chấp nhận ảnh JPG, PNG"<br>- File rejected | Edit mode active |

---

### Vendor Products & Orders

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| VEND13 | View vendor products list | 1. On vendor dashboard<br>2. Click "Sản phẩm" menu | - Table shows vendor's products<br>- Columns: Image, Name, Price, Stock, Status<br>- "Thêm sản phẩm" button<br>- Search available | Vendor has products |
| VEND14 | Toggle product status | 1. On products list<br>2. Click status toggle on a product<br>3. Confirm if prompted | - Confirmation dialog shows<br>- Status changes (Active/Inactive)<br>- Toast message shown | Product exists |
| VEND15 | View vendor orders | 1. On vendor dashboard<br>2. Click "Đơn hàng" menu | - Orders containing vendor products<br>- Columns: Order ID, Customer, Items, Total, Status<br>- Filter by status available | Vendor has orders |
| VEND16 | View order detail | 1. On vendor orders list<br>2. Click an order row | - Order detail opens<br>- Items with quantities shown<br>- Customer address (partial)<br>- Order timeline visible | Orders exist |
