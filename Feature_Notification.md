# Feature 10: Notification System - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_Notification |
| **Feature** | Notification System |
| **Module** | Notifications, Alerts, Real-time Updates |
| **Total Test Cases** | 12 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 10.1 Notification Bell Icon

| TC ID | TC_NTF_001 |
|-------|------------|
| **Description** | Verify notification bell icon in header |
| **Pre-conditions** | User logged in |
| **Procedure** | 1. Observe the navigation header<br>2. Locate notification bell icon |
| **Expected Results** | - Bell icon visible in header/navbar<br>- Icon positioned consistently (typically right side)<br>- Click area is appropriately sized<br>- Icon matches design system |

| TC ID | TC_NTF_002 |
|-------|------------|
| **Description** | Verify unread notification badge count |
| **Pre-conditions** | User has unread notifications |
| **Procedure** | 1. Observe notification bell icon<br>2. Check for badge/counter |
| **Expected Results** | - Red badge shows unread count<br>- Badge shows number (e.g., "5")<br>- "99+" shown if count exceeds 99<br>- Badge hidden when count is 0 |

| TC ID | TC_NTF_003 |
|-------|------------|
| **Description** | Verify notification badge updates real-time |
| **Pre-conditions** | User logged in, another action triggers notification |
| **Procedure** | 1. Note current badge count<br>2. Have another user/action trigger notification<br>3. Observe badge without refresh |
| **Expected Results** | - Badge count updates automatically<br>- No page refresh needed<br>- New notification animation (optional)<br>- Sound notification (if enabled) |

### 10.2 Notification Dropdown

| TC ID | TC_NTF_004 |
|-------|------------|
| **Description** | Verify notification dropdown opens |
| **Pre-conditions** | User logged in |
| **Procedure** | 1. Click on notification bell icon<br>2. Observe dropdown panel |
| **Expected Results** | - Dropdown panel opens below icon<br>- Smooth animation on open<br>- Header shows "Notifications"<br>- List of recent notifications displayed<br>- "View All" or "See More" link |

| TC ID | TC_NTF_005 |
|-------|------------|
| **Description** | Verify notification item display |
| **Pre-conditions** | User has notifications |
| **Procedure** | 1. Open notification dropdown<br>2. Observe a notification item |
| **Expected Results** | - Each item shows: Icon/Avatar, Title, Message preview<br>- Timestamp (e.g., "5 min ago", "Yesterday")<br>- Unread items have distinct styling (bold, background)<br>- Read items appear dimmer |

| TC ID | TC_NTF_006 |
|-------|------------|
| **Description** | Verify clicking notification navigates correctly |
| **Pre-conditions** | User has order-related notification |
| **Procedure** | 1. Open notification dropdown<br>2. Click on an order notification |
| **Expected Results** | - Dropdown closes<br>- Navigates to related page (order detail)<br>- Notification marked as read<br>- Badge count decrements |

| TC ID | TC_NTF_007 |
|-------|------------|
| **Description** | Verify empty notification state |
| **Pre-conditions** | User has no notifications |
| **Procedure** | 1. Click notification bell<br>2. Observe empty state |
| **Expected Results** | - Empty state illustration<br>- Message: "No notifications yet"<br>- Friendly text or icon<br>- Dropdown still functional |

### 10.3 Mark as Read

| TC ID | TC_NTF_008 |
|-------|------------|
| **Description** | Verify mark single notification as read |
| **Pre-conditions** | User has unread notifications |
| **Procedure** | 1. Open notification dropdown<br>2. Hover over unread notification<br>3. Click "Mark as read" option or checkmark |
| **Expected Results** | - Notification styling changes to read<br>- Badge count decrements by 1<br>- Action confirmed (subtle animation)<br>- No page reload needed |

| TC ID | TC_NTF_009 |
|-------|------------|
| **Description** | Verify "Mark all as read" functionality |
| **Pre-conditions** | User has multiple unread notifications |
| **Procedure** | 1. Open notification dropdown<br>2. Click "Mark all as read" button |
| **Expected Results** | - All notifications styled as read<br>- Badge count becomes 0<br>- Badge hidden or shows 0<br>- Success feedback (optional toast) |

### 10.4 Notification Page

| TC ID | TC_NTF_010 |
|-------|------------|
| **Description** | Verify full notifications page |
| **Pre-conditions** | User logged in |
| **Procedure** | 1. Click "View All" from dropdown<br>2. Or navigate to /notifications<br>3. Observe full page |
| **Expected Results** | - Full list of all notifications<br>- Pagination or infinite scroll<br>- Filter options (All, Unread, Read)<br>- Bulk actions available |

| TC ID | TC_NTF_011 |
|-------|------------|
| **Description** | Verify notification filter by type |
| **Pre-conditions** | User on notifications page |
| **Procedure** | 1. Click filter dropdown<br>2. Select "Orders" type<br>3. Observe filtered list |
| **Expected Results** | - Filter shows notification types: All, Orders, Messages, System<br>- List filters to selected type<br>- Count updates for filtered results<br>- Clear filter option |

| TC ID | TC_NTF_012 |
|-------|------------|
| **Description** | Verify delete/clear notifications |
| **Pre-conditions** | User has read notifications |
| **Procedure** | 1. On notifications page<br>2. Click "Clear all read" or delete icon<br>3. Confirm action |
| **Expected Results** | - Confirmation dialog for bulk delete<br>- After confirm: Read notifications removed<br>- Unread notifications preserved<br>- Success message displayed |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 12 |
| Priority - High | 5 |
| Priority - Medium | 5 |
| Priority - Low | 2 |
