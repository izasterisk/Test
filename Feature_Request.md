# Feature_Request - Support Request UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Support Request System |
| **Test requirement** | Support Tickets, Help Center pages available |
| **Number of TCs** | 12 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 12 | 0 |
| Round 2 | 0 | 0 | 12 | 0 |
| Round 3 | 0 | 0 | 12 | 0 |

---

## Test Cases

### Support Request List

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| REQ01 | View support request list | 1. Login<br>2. Navigate to "Hỗ trợ" section<br>3. Click "Yêu cầu của tôi" | - Ticket list displays<br>- Columns: ID, Subject, Status, Created, Updated<br>- Status badges (Mở, Đang xử lý, Đã giải quyết)<br>- "Tạo yêu cầu" button | Logged in |
| REQ02 | Empty request state | 1. Login (no requests)<br>2. Navigate to request list | - Empty state message<br>- "Bạn chưa có yêu cầu hỗ trợ nào"<br>- "Tạo yêu cầu" button prominent<br>- FAQ links shown | No requests exist |
| REQ03 | Filter by status | 1. On request list<br>2. Click status filter<br>3. Select "Đang mở" | - Filter shows: Tất cả, Mở, Đang xử lý, Đã giải quyết, Đã đóng<br>- List shows selected status only<br>- Count updates<br>- Clear filter option | Has requests |

---

### Create Support Request

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| REQ04 | View create request form | 1. On request list<br>2. Click "Tạo yêu cầu" | - Form with fields: Category, Subject, Description<br>- Category dropdown (Đơn hàng, Thanh toán, Kỹ thuật, Khác)<br>- Attachment upload option<br>- Gửi and Hủy buttons | Logged in |
| REQ05 | Create request - valid | 1. Open create form<br>2. Select Category: "Vấn đề đơn hàng"<br>3. Enter Subject: "Thiếu hàng trong đơn #12345"<br>4. Enter detailed description<br>5. Attach screenshot (optional)<br>6. Click "Gửi" | - Form validates<br>- Loading shows<br>- Success "Yêu cầu đã được gửi! Mã #XXX"<br>- Redirect to detail<br>- Email confirmation | Form open |
| REQ06 | Create request - validation | 1. Open create form<br>2. Leave all fields empty<br>3. Click "Gửi" | - Validation errors shown<br>- "Danh mục là bắt buộc"<br>- "Tiêu đề là bắt buộc"<br>- "Mô tả là bắt buộc"<br>- Form not submitted | Form open |
| REQ07 | Subject character limit | 1. Open create form<br>2. Enter subject > 200 characters | - Character counter (195/200)<br>- Input stops at max<br>- Or warning shown<br>- User informed | Form open |

---

### Request Detail View

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| REQ08 | View request detail | 1. On request list<br>2. Click a request row | - Full subject and description<br>- Status badge prominent<br>- Created date and updates<br>- Attachments downloadable<br>- Conversation thread below | Request exists |
| REQ09 | Reply to request | 1. On request detail (Open/In Progress)<br>2. Enter reply message<br>3. Click "Gửi phản hồi" | - Reply input visible<br>- Can attach files<br>- Reply added to conversation<br>- Timestamp and "Bạn" label<br>- Admin replies styled different | Request open |
| REQ10 | Cannot reply to closed | 1. Open closed request<br>2. Look for reply option | - Reply input disabled/hidden<br>- Message "Yêu cầu đã đóng"<br>- "Mở lại" option (if available)<br>- History still visible | Request closed |

---

### Request Status Updates

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| REQ11 | Status change notification | 1. Admin changes request status<br>2. User views request | - Status badge updated<br>- Change shown in timeline<br>- Notification received<br>- Email sent | Request exists |
| REQ12 | Close request by user | 1. On request detail (Resolved)<br>2. Click "Đóng yêu cầu"<br>3. Optional: Leave feedback<br>4. Confirm | - Confirmation dialog<br>- Optional satisfaction rating<br>- After confirm: Status = "Đã đóng"<br>- Limited reopen option | Request resolved |
