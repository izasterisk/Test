# Feature_Notification - Notification UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Notification |
| **Test requirement** | Notification bell component available |
| **Number of TCs** | 4 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 4 | 0 |
| Round 2 | 0 | 0 | 4 | 0 |
| Round 3 | 0 | 0 | 4 | 0 |

---

## Test Cases

### Notification Bell (Header Component)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| NOTI01 | View notification bell | 1. Login as any user<br>2. Look at header/navbar | - Bell icon visible in header<br>- Badge shows unread count (if any)<br>- Clickable | Logged in |
| NOTI02 | Open notification dropdown | 1. Login<br>2. Click on notification bell icon | - Dropdown/popover opens<br>- Notification list shows<br>- Each item: title, message, time<br>- Unread items highlighted<br>- "Xem tất cả" link (if applicable) | Logged in |
| NOTI03 | Mark notification as read | 1. Open notification dropdown<br>2. Click on an unread notification | - Notification marked as read<br>- Highlight removed<br>- Badge count decreases<br>- May navigate to related page | Has unread notifications |
| NOTI04 | Empty notifications state | 1. Login (account with no notifications)<br>2. Click notification bell | - Dropdown opens<br>- "Không có thông báo" message<br>- Empty state illustration | No notifications |
