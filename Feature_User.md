# Feature_User - User Management UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | User Management |
| **Test requirement** | Profile page, Change password page available |
| **Number of TCs** | 15 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 15 | 0 |
| Round 2 | 0 | 0 | 15 | 0 |
| Round 3 | 0 | 0 | 15 | 0 |

---

## Test Cases

### Profile Page (/profile)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER01 | View profile information | 1. Login as customer<br>2. Navigate to /profile page | - Profile page displays<br>- Full name, email, phone shown<br>- Avatar displayed (or default)<br>- Role badge shows "Customer" | Logged in |
| USER02 | Edit profile - change name successfully | 1. Go to /profile<br>2. Click "Chỉnh sửa" button<br>3. Change full name to "New Name"<br>4. Click "Lưu" | - Edit form opens<br>- Loading spinner on save<br>- Success toast shows<br>- Name updated on profile | Logged in |
| USER03 | Edit profile - change phone successfully | 1. Go to /profile<br>2. Click "Chỉnh sửa"<br>3. Change phone to "0999888777"<br>4. Click "Lưu" | - Phone field editable<br>- Success toast shows<br>- Phone updated on profile | Logged in |
| USER04 | Edit profile - empty name validation | 1. Go to /profile<br>2. Click "Chỉnh sửa"<br>3. Clear full name field<br>4. Click "Lưu" | - Validation error shows<br>- "Họ tên không được để trống"<br>- Form not submitted | Logged in |
| USER05 | Edit profile - cancel edit | 1. Go to /profile<br>2. Click "Chỉnh sửa"<br>3. Change some fields<br>4. Click "Hủy" | - Edit form closes<br>- Original values restored<br>- No changes saved | Logged in |

---

### Avatar Upload

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER06 | Upload avatar - valid image | 1. Go to /profile<br>2. Click on avatar area<br>3. Select a valid JPG file (< 5MB)<br>4. Confirm upload | - File dialog opens<br>- Image preview shows<br>- Upload progress/loading<br>- New avatar displayed | Logged in |
| USER07 | Upload avatar - invalid file type | 1. Go to /profile<br>2. Click on avatar area<br>3. Select a .txt or .pdf file | - File rejected<br>- Error message "Chỉ chấp nhận file ảnh"<br>- Avatar unchanged | Logged in |
| USER08 | Upload avatar - file too large | 1. Go to /profile<br>2. Click on avatar area<br>3. Select an image > 10MB | - File rejected<br>- Error message about file size<br>- Avatar unchanged | Logged in |

---

### Address Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER09 | Add new address successfully | 1. Go to /profile<br>2. Click "Thêm địa chỉ"<br>3. Select Tỉnh/Thành<br>4. Select Quận/Huyện<br>5. Select Xã/Phường<br>6. Enter specific address<br>7. Click on map to select location<br>8. Click "Lưu" | - Address dialog opens<br>- Cascading dropdowns work<br>- Map marker can be placed<br>- Address saved successfully<br>- New address in list | Logged in |
| USER10 | Add address - missing required fields | 1. Go to /profile<br>2. Click "Thêm địa chỉ"<br>3. Leave Tỉnh/Thành empty<br>4. Click "Lưu" | - Validation errors show<br>- "Vui lòng chọn tỉnh/thành"<br>- Form not submitted | Logged in |
| USER11 | Add address - no map location | 1. Go to /profile<br>2. Click "Thêm địa chỉ"<br>3. Fill all dropdowns<br>4. Don't select map location<br>5. Click "Lưu" | - Validation error<br>- "Vui lòng chọn vị trí trên bản đồ"<br>- Form not submitted | Logged in |
| USER12 | Edit existing address | 1. Go to /profile<br>2. Find existing address<br>3. Click "Cập nhật"<br>4. Change district<br>5. Click "Cập nhật" | - Edit dialog with current values<br>- Changes saved<br>- Updated address displayed | Has address |
| USER13 | Delete address - confirm | 1. Go to /profile<br>2. Find existing address<br>3. Click trash icon<br>4. Click "Đồng ý" in confirmation | - Confirmation dialog shows<br>- Address removed from list<br>- Success feedback | Has address |
| USER14 | Delete address - cancel | 1. Go to /profile<br>2. Find existing address<br>3. Click trash icon<br>4. Click "Hủy" in confirmation | - Confirmation dialog shows<br>- Dialog closes<br>- Address not deleted | Has address |

---

### Change Password (/change-password)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER15 | Navigate to change password | 1. Go to /profile<br>2. Click "Đổi mật khẩu" button | - Navigate to /change-password<br>- Change password form displays<br>- Fields: Old password, New password, Confirm | Logged in |
