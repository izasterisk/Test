# Feature_User - User Management UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | User Management |
| **Test requirement** | Profile page available |
| **Number of TCs** | 7 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 7 | 0 |
| Round 2 | 0 | 0 | 7 | 0 |
| Round 3 | 0 | 0 | 7 | 0 |

---

## Test Cases

### Profile Page (/profile)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER01 | View profile information | 1. Login as customer<br>2. Navigate to /profile page | - Profile page displays<br>- Full name, email, phone shown<br>- Avatar shown<br>- Role badge displayed | Logged in |
| USER02 | Edit profile successfully | 1. Go to /profile<br>2. Click "Chỉnh sửa" button<br>3. Change full name to "New Name"<br>4. Change phone to "0999888777"<br>5. Click "Lưu" button | - Edit form shows<br>- Loading spinner on save<br>- Success toast shows<br>- Profile updated with new info | Logged in |
| USER03 | Edit profile with empty name | 1. Go to /profile<br>2. Click "Chỉnh sửa"<br>3. Clear full name field<br>4. Click "Lưu" | - Validation error shows<br>- Form not submitted<br>- "Họ tên không được để trống" | Logged in |
| USER04 | Upload avatar successfully | 1. Go to /profile<br>2. Click on avatar area<br>3. Select a valid image file (jpg, png)<br>4. Confirm upload | - Image preview shows<br>- Upload progress/loading<br>- New avatar displayed<br>- Success message | Logged in |

---

### Address Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| USER05 | Add new address | 1. Go to /profile<br>2. Click "Thêm địa chỉ"<br>3. Fill address form:<br>- Select Tỉnh/Thành<br>- Select Quận/Huyện<br>- Select Xã/Phường<br>- Enter specific address<br>4. Click on map to select location<br>5. Click "Lưu" | - Address dialog opens<br>- Dropdowns work correctly<br>- Map marker placed<br>- Address saved<br>- New address in list | Logged in |
| USER06 | Edit existing address | 1. Go to /profile<br>2. Find existing address<br>3. Click "Cập nhật"<br>4. Change address details<br>5. Click "Cập nhật" | - Edit dialog opens with current values<br>- Changes saved<br>- Updated address displayed | Logged in, has address |
| USER07 | Delete address | 1. Go to /profile<br>2. Find existing address<br>3. Click delete (trash) icon<br>4. Confirm deletion in dialog | - Confirmation dialog shows<br>- Address removed from list<br>- No error message | Logged in, has address |
