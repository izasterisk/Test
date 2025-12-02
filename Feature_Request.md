# Feature 11: Support Request/Ticket - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_Request |
| **Feature** | Support Request System |
| **Module** | Support Tickets, Help Center |
| **Total Test Cases** | 12 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 11.1 Support Request List

| TC ID | TC_REQ_001 |
|-------|------------|
| **Description** | Verify support request list page |
| **Pre-conditions** | User logged in |
| **Procedure** | 1. Navigate to "Support" or "Help" section<br>2. Click on "My Requests" or similar |
| **Expected Results** | - Page displays list of user's tickets<br>- Table columns: ID, Subject, Status, Created Date, Last Update<br>- Status badges with colors (Open, In Progress, Resolved)<br>- "Create New Request" button visible |

| TC ID | TC_REQ_002 |
|-------|------------|
| **Description** | Verify empty state - no requests |
| **Pre-conditions** | User has no support requests |
| **Procedure** | 1. Navigate to support request list<br>2. Observe empty state |
| **Expected Results** | - Empty state message displayed<br>- "You haven't submitted any requests"<br>- "Create Request" button prominent<br>- Help resources or FAQ links shown |

| TC ID | TC_REQ_003 |
|-------|------------|
| **Description** | Verify filter requests by status |
| **Pre-conditions** | User has multiple requests |
| **Procedure** | 1. Click status filter dropdown<br>2. Select "Open" status<br>3. Observe filtered results |
| **Expected Results** | - Filter dropdown shows: All, Open, In Progress, Resolved, Closed<br>- List shows only selected status<br>- Count indicator updates<br>- Clear filter option available |

### 11.2 Create Support Request

| TC ID | TC_REQ_004 |
|-------|------------|
| **Description** | Verify create request form layout |
| **Pre-conditions** | User logged in |
| **Procedure** | 1. Click "Create New Request" button<br>2. Observe the form |
| **Expected Results** | - Form with fields: Category, Subject, Description<br>- Category dropdown (Order Issue, Payment, Technical, Other)<br>- Attachment upload option<br>- Submit and Cancel buttons<br>- Required fields marked |

| TC ID | TC_REQ_005 |
|-------|------------|
| **Description** | Verify create request with valid data |
| **Pre-conditions** | User on create request form |
| **Procedure** | 1. Select Category: "Order Issue"<br>2. Enter Subject: "Missing item in my order #12345"<br>3. Enter detailed description<br>4. Attach screenshot (optional)<br>5. Click "Submit" |
| **Expected Results** | - Form validates successfully<br>- Loading indicator during submission<br>- Success: "Request submitted! Ticket #XXX created"<br>- Redirected to request detail<br>- Email confirmation sent (info shown) |

| TC ID | TC_REQ_006 |
|-------|------------|
| **Description** | Verify create request - validation errors |
| **Pre-conditions** | User on create request form |
| **Procedure** | 1. Leave all fields empty<br>2. Click "Submit" |
| **Expected Results** | - Validation errors displayed<br>- "Category is required"<br>- "Subject is required"<br>- "Description is required"<br>- Form does not submit |

| TC ID | TC_REQ_007 |
|-------|------------|
| **Description** | Verify subject character limit |
| **Pre-conditions** | User on create request form |
| **Procedure** | 1. Enter subject exceeding 200 characters<br>2. Observe behavior |
| **Expected Results** | - Character counter shows limit (e.g., 195/200)<br>- Input stops accepting at max<br>- Or warning message shown<br>- User informed of limit |

### 11.3 Request Detail View

| TC ID | TC_REQ_008 |
|-------|------------|
| **Description** | Verify request detail page |
| **Pre-conditions** | User has at least one request |
| **Procedure** | 1. Click on a request from list<br>2. Observe detail page |
| **Expected Results** | - Full subject and description displayed<br>- Status badge prominently shown<br>- Creation date and last update<br>- Attached files downloadable<br>- Conversation/Reply thread below |

| TC ID | TC_REQ_009 |
|-------|------------|
| **Description** | Verify reply to request |
| **Pre-conditions** | User on request detail, status is "Open" or "In Progress" |
| **Procedure** | 1. Scroll to reply section<br>2. Enter reply message<br>3. Click "Send Reply" |
| **Expected Results** | - Reply input area visible<br>- Can attach files to reply<br>- Success: Reply added to conversation<br>- Timestamp and "You" label shown<br>- Admin replies styled differently |

| TC ID | TC_REQ_010 |
|-------|------------|
| **Description** | Verify cannot reply to closed request |
| **Pre-conditions** | Request has status "Closed" |
| **Procedure** | 1. Open a closed request<br>2. Look for reply option |
| **Expected Results** | - Reply input disabled or hidden<br>- Message: "This request is closed"<br>- "Reopen Request" option may be available<br>- Conversation history still visible |

### 11.4 Request Status Updates

| TC ID | TC_REQ_011 |
|-------|------------|
| **Description** | Verify status change notification |
| **Pre-conditions** | User has open request |
| **Procedure** | 1. Admin changes request status<br>2. User views the request |
| **Expected Results** | - Status badge updated to new status<br>- Status change shown in timeline<br>- Notification received (if enabled)<br>- Email notification sent |

| TC ID | TC_REQ_012 |
|-------|------------|
| **Description** | Verify close request by user |
| **Pre-conditions** | User on own request detail, status is "Resolved" |
| **Procedure** | 1. Click "Close Request" button<br>2. Optionally leave feedback<br>3. Confirm action |
| **Expected Results** | - Confirmation dialog appears<br>- Optional satisfaction rating<br>- After confirm: Status changes to "Closed"<br>- Cannot be reopened (or limited reopen option) |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 12 |
| Priority - High | 5 |
| Priority - Medium | 5 |
| Priority - Low | 2 |
