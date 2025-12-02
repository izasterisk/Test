# Feature_Request - Request & Support UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Request & Support |
| **Test requirement** | Ticket page available |
| **Number of TCs** | 5 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 5 | 0 |
| Round 2 | 0 | 0 | 5 | 0 |
| Round 3 | 0 | 0 | 5 | 0 |

---

## Test Cases

### Ticket Page (/ticket)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| REQ01 | View ticket list | 1. Login<br>2. Navigate to /ticket or Support page | - Ticket list displays<br>- Each ticket: ID, title, status, date<br>- Status badges (Pending, Processing, Resolved)<br>- "Tạo yêu cầu mới" button | Logged in |
| REQ02 | Create support ticket | 1. Go to ticket page<br>2. Click "Tạo yêu cầu mới"<br>3. Fill form:<br>- Select ticket type (Support/Refund)<br>- Enter title<br>- Enter description<br>- Attach files (optional)<br>4. Click submit | - Create form/modal opens<br>- Type dropdown works<br>- Text fields work<br>- File upload works<br>- Success toast "Yêu cầu đã được gửi"<br>- New ticket in list | Logged in |
| REQ03 | Create ticket with empty fields | 1. Go to create ticket form<br>2. Leave title empty<br>3. Click submit | - Validation error shows<br>- "Tiêu đề không được để trống"<br>- Form not submitted | Logged in |
| REQ04 | View ticket detail | 1. Go to ticket list<br>2. Click on a ticket row | - Ticket detail page/modal opens<br>- Full description shown<br>- Attachments visible<br>- Status and timeline shown<br>- Response from staff (if any) | Ticket exists |
| REQ05 | Filter tickets by status | 1. Go to ticket list<br>2. Click on status filter<br>3. Select "Đang xử lý" | - Tickets filtered by status<br>- Only matching tickets shown<br>- Filter indicator active | Has multiple tickets |
