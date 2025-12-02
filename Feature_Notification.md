# Feature_Notification - Notification UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Notification System |
| **Test requirement** | Notification Bell, List, Real-time Updates available |
| **Number of TCs** | 12 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 12 | 0 |
| Round 2 | 0 | 0 | 12 | 0 |
| Round 3 | 0 | 0 | 12 | 0 |

---

## Test Cases

### Notification Bell Icon

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| NOTI01 | View notification bell | 1. Login<br>2. Observe navbar header | - Bell icon visible in navbar<br>- Position consistent (right side)<br>- Click area sized appropriately<br>- Icon matches design | Logged in |
| NOTI02 | Unread notification badge | 1. Login (has unread notifications)<br>2. Observe bell icon | - Red badge shows unread count<br>- Badge shows number (e.g., "5")<br>- "99+" if count > 99<br>- Badge hidden when count = 0 | Has unread notifications |
| NOTI03 | Real-time badge update | 1. Login<br>2. Note badge count<br>3. Trigger new notification (another action)<br>4. Observe without refresh | - Badge count updates auto<br>- No page refresh needed<br>- Animation on new notification<br>- Sound (if enabled) | Logged in |

---

### Notification Dropdown

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| NOTI04 | Open notification dropdown | 1. Login<br>2. Click bell icon | - Dropdown panel opens<br>- Smooth animation<br>- Header "Thông báo"<br>- Recent notifications listed<br>- "Xem tất cả" link | Logged in |
| NOTI05 | View notification item | 1. Open notification dropdown<br>2. Observe a notification | - Icon/Avatar shown<br>- Title and preview text<br>- Timestamp (e.g., "5 phút trước")<br>- Unread items bold/highlighted<br>- Read items dimmer | Has notifications |
| NOTI06 | Click notification to navigate | 1. Open dropdown<br>2. Click order notification | - Dropdown closes<br>- Navigate to related page<br>- Notification marked read<br>- Badge count decrements | Has order notification |
| NOTI07 | Empty notification state | 1. Login (no notifications)<br>2. Click bell icon | - Empty state illustration<br>- "Chưa có thông báo nào"<br>- Friendly icon<br>- Dropdown functional | No notifications |

---

### Mark as Read

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| NOTI08 | Mark single as read | 1. Open dropdown<br>2. Hover unread notification<br>3. Click "Đánh dấu đã đọc" | - Notification styling changes<br>- Badge count decrements<br>- Subtle animation<br>- No page reload | Has unread |
| NOTI09 | Mark all as read | 1. Open dropdown<br>2. Click "Đánh dấu tất cả đã đọc" | - All notifications styled as read<br>- Badge count becomes 0<br>- Badge hidden<br>- Success feedback | Multiple unread |

---

### Notification Page

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| NOTI10 | View all notifications page | 1. Click "Xem tất cả" from dropdown<br>2. Or navigate to /notifications | - Full notification list<br>- Pagination or infinite scroll<br>- Filter: Tất cả, Chưa đọc, Đã đọc<br>- Bulk actions available | Logged in |
| NOTI11 | Filter by type | 1. On notifications page<br>2. Click filter dropdown<br>3. Select "Đơn hàng" | - Filter shows types: Tất cả, Đơn hàng, Tin nhắn, Hệ thống<br>- List filters to type<br>- Count updates<br>- Clear filter option | Has notifications |
| NOTI12 | Clear/Delete notifications | 1. On notifications page<br>2. Click "Xóa đã đọc"<br>3. Confirm action | - Confirmation dialog<br>- After confirm: Read notifications removed<br>- Unread preserved<br>- Success message | Has read notifications |
