# Feature_User - User Management UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | User Management |
| **Test requirement** | Profile, Edit Profile, Address Management pages available |
| **Number of TCs** | 12 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 12 | 0 |
| Round 2 | 0 | 0 | 12 | 0 |
| Round 3 | 0 | 0 | 12 | 0 |

---

## Test Cases

### Profile Page (/profile)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER01 | View profile page | 1. Login as customer<br>2. Click avatar/profile in navbar<br>3. Navigate to /profile | - Profile page displays<br>- User avatar shown<br>- Full name, email, phone visible<br>- Edit button available | Logged in |
| USER02 | Edit profile - update full name | 1. Open /profile<br>2. Click "Chỉnh sửa" button<br>3. Change Họ tên to "Updated Name"<br>4. Click "Lưu" | - Loading spinner shows<br>- Success toast "Cập nhật thành công"<br>- Profile shows updated name | Logged in |
| USER03 | Edit profile - invalid phone format | 1. Open /profile edit mode<br>2. Change SĐT to "abc123"<br>3. Click "Lưu" | - Validation error shows<br>- "Số điện thoại không hợp lệ"<br>- Form not submitted | Logged in |
| USER04 | Edit profile - empty required field | 1. Open /profile edit mode<br>2. Clear Họ tên field<br>3. Click "Lưu" | - Validation error "Họ tên là bắt buộc"<br>- Form not submitted | Logged in |
| USER05 | Cancel profile edit | 1. Open /profile edit mode<br>2. Make some changes<br>3. Click "Hủy" button | - Edit mode closes<br>- Original data restored<br>- Changes discarded | Logged in |

---

### Avatar Upload

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER06 | Upload avatar - valid image | 1. Open /profile<br>2. Click avatar area or camera icon<br>3. Select JPG image (< 5MB)<br>4. Confirm upload | - Upload progress shows<br>- New avatar displays<br>- Success toast shown | Logged in |
| USER07 | Upload avatar - invalid file type | 1. Open /profile<br>2. Click avatar upload<br>3. Select .pdf file | - Error "Chỉ chấp nhận file ảnh JPG, PNG"<br>- File rejected | Logged in |
| USER08 | Upload avatar - oversized file | 1. Open /profile<br>2. Click avatar upload<br>3. Select image > 5MB | - Error "File vượt quá 5MB"<br>- File rejected | Logged in |

---

### Address Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER09 | View address list | 1. Open /profile<br>2. Scroll to address section | - Address list displays<br>- Each address shows: Name, Phone, Full address<br>- Default badge on primary address<br>- "Thêm địa chỉ" button visible | Logged in |
| USER10 | Add new address | 1. Open address section<br>2. Click "Thêm địa chỉ"<br>3. Fill: Tên = "Văn phòng"<br>4. Fill: SĐT = "0901234567"<br>5. Select Province, District, Ward<br>6. Fill detail address<br>7. Click "Lưu" | - Loading shows<br>- Success toast<br>- New address in list | Logged in |
| USER11 | Add address - missing fields | 1. Open add address form<br>2. Leave Province empty<br>3. Click "Lưu" | - Validation errors show<br>- "Vui lòng chọn Tỉnh/Thành phố"<br>- Form not submitted | Logged in |
| USER12 | Delete address | 1. Open address list<br>2. Click delete icon on an address<br>3. Confirm deletion | - Confirmation dialog shows<br>- After confirm: Address removed<br>- Success toast displayed | Logged in, has ≥2 addresses |
