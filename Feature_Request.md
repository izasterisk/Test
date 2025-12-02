# Feature_Request - Request & Support Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Request & Support |
| **Test requirement** | API and design are available |
| **Number of TCs** | 10 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 10 | 0 |
| Round 2 | 0 | 0 | 10 | 0 |
| Round 3 | 0 | 0 | 10 | 0 |

---

## Test Cases

### Create Request

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| REQ01 | Create support request | 1. Login<br>2. Call POST `/api/RequestTicket`<br>3. Send requestType=SupportRequest, message | - Request created (Pending)<br>- Status 201 Created | Logged in |
| REQ02 | Create refund request | 1. Login<br>2. Call POST `/api/RequestTicket`<br>3. Send requestType=RefundRequest, orderId | - Refund request created<br>- Linked to order<br>- Status 201 Created | Logged in, has order |
| REQ03 | Get request by ID | 1. Login<br>2. Call GET `/api/RequestTicket/{requestId}` | - Request details returned<br>- Includes messages | Request exists |
| REQ04 | Get my requests | 1. Login<br>2. Call GET `/api/RequestTicket/my-requests?page=1` | - List of user's requests<br>- Status 200 OK | Logged in |

---

### Request Messages

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| REQ05 | Send new message | 1. Login<br>2. Call POST `/api/RequestTicket/{requestId}/message`<br>3. Send message content | - Message added to request<br>- Status 201 Created | Request exists |
| REQ06 | Send 4th message (not allowed) | 1. Login<br>2. Request already has 3 messages<br>3. Try to send 4th message | - Error: Max 3 messages<br>- Status 400 Bad Request | Request with 3 messages |

---

### Process Request (Admin/Staff)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| REQ07 | Get all requests (Admin/Staff) | 1. Login as Admin/Staff<br>2. Call GET `/api/RequestTicket?page=1` | - List of all requests<br>- Status 200 OK | Logged in as Admin/Staff |
| REQ08 | Filter requests by type | 1. Login as Admin/Staff<br>2. Call GET `/api/RequestTicket?requestType=RefundRequest` | - Only refund requests returned | Requests exist |
| REQ09 | Approve request | 1. Login as Admin/Staff<br>2. Call PATCH `/api/RequestTicket/{requestId}/process`<br>3. Send status=Approved, responseNote | - Request approved<br>- Status 200 OK | Pending request exists |
| REQ10 | Reject request with reason | 1. Login as Admin/Staff<br>2. Call PATCH `/api/RequestTicket/{requestId}/process`<br>3. Send status=Rejected, responseNote | - Request rejected<br>- Reason saved<br>- Status 200 OK | Pending request exists |
