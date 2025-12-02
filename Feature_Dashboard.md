# Feature 13: Admin/Staff Dashboard - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_Dashboard |
| **Feature** | Admin/Staff Dashboard |
| **Module** | Dashboard, Analytics, System Management |
| **Total Test Cases** | 14 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 13.1 Dashboard Layout

| TC ID | TC_DASH_001 |
|-------|------------|
| **Description** | Verify admin dashboard main layout |
| **Pre-conditions** | User logged in as Admin |
| **Procedure** | 1. Navigate to Admin Dashboard<br>2. Observe the main page layout |
| **Expected Results** | - Dashboard header with admin name and avatar<br>- Left sidebar navigation<br>- Main content area with stats cards<br>- Recent activity section<br>- Quick action buttons |

| TC ID | TC_DASH_002 |
|-------|------------|
| **Description** | Verify staff dashboard layout (limited access) |
| **Pre-conditions** | User logged in as Staff |
| **Procedure** | 1. Navigate to Staff Dashboard<br>2. Compare with admin dashboard |
| **Expected Results** | - Similar layout to admin<br>- Some menu items hidden (role-based)<br>- Stats relevant to staff role<br>- No access to admin-only features |

| TC ID | TC_DASH_003 |
|-------|------------|
| **Description** | Verify sidebar navigation menu |
| **Pre-conditions** | User on admin dashboard |
| **Procedure** | 1. Observe left sidebar menu<br>2. Click each menu item |
| **Expected Results** | - Menu shows: Dashboard, Users, Products, Orders, Reports, Settings<br>- Active item highlighted<br>- Submenu expands on click (if applicable)<br>- Navigation works correctly |

| TC ID | TC_DASH_004 |
|-------|------------|
| **Description** | Verify sidebar collapse functionality |
| **Pre-conditions** | User on dashboard |
| **Procedure** | 1. Click collapse/hamburger icon<br>2. Observe sidebar behavior<br>3. Click again to expand |
| **Expected Results** | - Sidebar collapses to icons only<br>- Main content area expands<br>- Tooltip shows menu name on hover<br>- Expand restores full sidebar |

### 13.2 Dashboard Statistics Cards

| TC ID | TC_DASH_005 |
|-------|------------|
| **Description** | Verify stats cards display |
| **Pre-conditions** | Admin on dashboard |
| **Procedure** | 1. Observe statistics cards at top<br>2. Check displayed metrics |
| **Expected Results** | - Cards show: Total Users, Total Orders, Revenue, Products<br>- Numbers formatted properly (1.5K, ₫1.2M)<br>- Comparison with previous period (↑12%)<br>- Card icons relevant to metric |

| TC ID | TC_DASH_006 |
|-------|------------|
| **Description** | Verify stats cards click navigation |
| **Pre-conditions** | Admin on dashboard |
| **Procedure** | 1. Click on "Total Orders" card<br>2. Observe navigation |
| **Expected Results** | - Navigates to Orders management page<br>- Or opens detailed view modal<br>- Breadcrumb updates<br>- Back button returns to dashboard |

| TC ID | TC_DASH_007 |
|-------|------------|
| **Description** | Verify dashboard data refresh |
| **Pre-conditions** | Admin on dashboard |
| **Procedure** | 1. Note current stats values<br>2. Click refresh button or wait for auto-refresh<br>3. Observe updates |
| **Expected Results** | - Loading indicator during refresh<br>- Stats update with latest data<br>- Last updated timestamp shown<br>- No page reload required |

### 13.3 Charts & Analytics

| TC ID | TC_DASH_008 |
|-------|------------|
| **Description** | Verify revenue chart display |
| **Pre-conditions** | Admin on dashboard |
| **Procedure** | 1. Scroll to charts section<br>2. Observe revenue chart |
| **Expected Results** | - Line or bar chart displays<br>- X-axis: Time period (days/weeks)<br>- Y-axis: Revenue amount<br>- Hover shows exact values<br>- Legend visible |

| TC ID | TC_DASH_009 |
|-------|------------|
| **Description** | Verify chart time period filter |
| **Pre-conditions** | Admin viewing chart |
| **Procedure** | 1. Click time period selector<br>2. Change from "Last 7 days" to "Last 30 days"<br>3. Observe chart update |
| **Expected Results** | - Time period options: 7 days, 30 days, 90 days, Year<br>- Chart data updates accordingly<br>- Smooth transition animation<br>- Period reflected in chart labels |

| TC ID | TC_DASH_010 |
|-------|------------|
| **Description** | Verify chart export functionality |
| **Pre-conditions** | Admin viewing chart |
| **Procedure** | 1. Click export/download icon on chart<br>2. Select export format |
| **Expected Results** | - Export options: PNG, PDF, CSV<br>- File downloads successfully<br>- Chart/data exported correctly<br>- Filename includes date |

### 13.4 Recent Activity & Tables

| TC ID | TC_DASH_011 |
|-------|------------|
| **Description** | Verify recent orders table on dashboard |
| **Pre-conditions** | System has recent orders |
| **Procedure** | 1. Scroll to "Recent Orders" section<br>2. Observe table data |
| **Expected Results** | - Table shows 5-10 most recent orders<br>- Columns: Order ID, Customer, Amount, Status, Date<br>- Status badges with colors<br>- "View All" link to orders page |

| TC ID | TC_DASH_012 |
|-------|------------|
| **Description** | Verify recent users registration list |
| **Pre-conditions** | System has recent user registrations |
| **Procedure** | 1. Locate "New Users" section<br>2. Observe the list |
| **Expected Results** | - Shows recent user registrations<br>- Each entry: Avatar, Name, Email, Date<br>- Click navigates to user detail<br>- Count of new users today |

### 13.5 Access Control

| TC ID | TC_DASH_013 |
|-------|------------|
| **Description** | Verify unauthorized access redirect |
| **Pre-conditions** | User logged in as regular Customer |
| **Procedure** | 1. Try to access /admin/dashboard directly<br>2. Observe behavior |
| **Expected Results** | - Access denied or redirected<br>- Error message: "You don't have permission"<br>- Redirected to home or login<br>- No dashboard data exposed |

| TC ID | TC_DASH_014 |
|-------|------------|
| **Description** | Verify role-based menu visibility |
| **Pre-conditions** | Compare Admin vs Staff login |
| **Procedure** | 1. Login as Admin, note menu items<br>2. Login as Staff, note menu items<br>3. Compare differences |
| **Expected Results** | - Admin sees all menu items<br>- Staff sees limited items<br>- "User Management" hidden for staff<br>- "System Settings" admin-only |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 14 |
| Priority - High | 6 |
| Priority - Medium | 5 |
| Priority - Low | 3 |
