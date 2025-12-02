# Feature_Notification - Notification Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Notification |
| **Test requirement** | API and design are available |
| **Number of TCs** | 6 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 6 | 0 |
| Round 2 | 0 | 0 | 6 | 0 |
| Round 3 | 0 | 0 | 6 | 0 |

---

## Test Cases

### Notification Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| NOTI01 | Get user notifications | 1. Login<br>2. Call GET `/api/Notification/user/{userId}?page=1&pageSize=10` | - List of notifications returned<br>- Ordered by date (newest first)<br>- Status 200 OK | Logged in, has notifications |
| NOTI02 | Get notifications with empty result | 1. Login as new user<br>2. Call GET `/api/Notification/user/{userId}` | - Empty list returned<br>- Status 200 OK | Logged in, no notifications |
| NOTI03 | Mark notification as read | 1. Login<br>2. Call PATCH `/api/Notification/{id}/revert-read-status`<br>3. Notification is unread | - Notification marked as read<br>- IsRead = true<br>- Status 200 OK | Unread notification exists |
| NOTI04 | Mark notification as unread | 1. Login<br>2. Call PATCH `/api/Notification/{id}/revert-read-status`<br>3. Notification is read | - Notification marked as unread<br>- IsRead = false<br>- Status 200 OK | Read notification exists |
| NOTI05 | Delete notification | 1. Login<br>2. Call DELETE `/api/Notification/{id}` | - Notification deleted<br>- Status 200 OK | Notification exists |
| NOTI06 | Delete non-existent notification | 1. Login<br>2. Call DELETE `/api/Notification/99999` | - Error: Cannot delete<br>- Status 400 Bad Request | None |
