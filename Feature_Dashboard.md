# Feature_Dashboard - Admin/Staff Dashboard UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Admin/Staff Dashboard |
| **Test requirement** | Dashboard, Analytics, System Management available |
| **Number of TCs** | 14 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 14 | 0 |
| Round 2 | 0 | 0 | 14 | 0 |
| Round 3 | 0 | 0 | 14 | 0 |

---

## Test Cases

### Dashboard Layout

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH01 | View admin dashboard | 1. Login as Admin<br>2. Navigate to /admin | - Dashboard header with admin name<br>- Left sidebar navigation<br>- Stats cards in main area<br>- Recent activity section<br>- Quick action buttons | Logged in as Admin |
| DASH02 | View staff dashboard | 1. Login as Staff<br>2. Navigate to dashboard | - Similar layout to admin<br>- Some menus hidden (role-based)<br>- Staff-relevant stats<br>- No admin-only features | Logged in as Staff |
| DASH03 | Sidebar navigation | 1. On admin dashboard<br>2. Observe left sidebar<br>3. Click each menu item | - Menu: Dashboard, Users, Products, Orders, Reports, Settings<br>- Active item highlighted<br>- Submenu expands if applicable<br>- Navigation works | Dashboard open |
| DASH04 | Sidebar collapse | 1. On dashboard<br>2. Click collapse icon<br>3. Click again to expand | - Sidebar collapses to icons<br>- Main area expands<br>- Tooltip on hover<br>- Expand restores full sidebar | Dashboard open |

---

### Dashboard Statistics Cards

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH05 | View stats cards | 1. On admin dashboard<br>2. Observe top stats cards | - Cards: Total Users, Orders, Revenue, Products<br>- Numbers formatted (1.5K, ₫1.2M)<br>- Comparison % (↑12%)<br>- Card icons relevant | Dashboard open |
| DASH06 | Stats card click | 1. On dashboard<br>2. Click "Tổng đơn hàng" card | - Navigate to Orders page<br>- Or detailed view modal<br>- Breadcrumb updates<br>- Back returns to dashboard | Stats cards visible |
| DASH07 | Refresh dashboard data | 1. On dashboard<br>2. Note current stats<br>3. Click refresh button | - Loading indicator<br>- Stats update with latest<br>- "Cập nhật lúc" timestamp<br>- No page reload | Dashboard open |

---

### Charts & Analytics

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH08 | View revenue chart | 1. On dashboard<br>2. Scroll to charts section | - Line/bar chart displays<br>- X-axis: Time period<br>- Y-axis: Revenue<br>- Hover shows values<br>- Legend visible | Dashboard open |
| DASH09 | Chart time period filter | 1. On chart section<br>2. Click time selector<br>3. Change "7 ngày" to "30 ngày" | - Options: 7 ngày, 30 ngày, 90 ngày, Năm<br>- Chart data updates<br>- Smooth transition<br>- Labels update | Chart visible |
| DASH10 | Chart export | 1. On chart<br>2. Click export/download icon | - Export options: PNG, PDF, CSV<br>- File downloads<br>- Data exported correctly<br>- Filename includes date | Chart visible |

---

### Recent Activity & Tables

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH11 | Recent orders table | 1. On dashboard<br>2. Scroll to "Đơn hàng gần đây" | - Table shows 5-10 recent orders<br>- Columns: ID, Customer, Amount, Status, Date<br>- Status badges colored<br>- "Xem tất cả" link | Orders exist |
| DASH12 | Recent users list | 1. On dashboard<br>2. Locate "Người dùng mới" section | - Recent registrations shown<br>- Avatar, Name, Email, Date<br>- Click navigates to user<br>- Count of new users today | Users exist |

---

### Access Control

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH13 | Unauthorized access redirect | 1. Login as Customer<br>2. Try access /admin/dashboard | - Access denied or redirect<br>- "Bạn không có quyền truy cập"<br>- Redirect to home/login<br>- No dashboard data exposed | Logged as Customer |
| DASH14 | Role-based menu visibility | 1. Login as Admin, note menus<br>2. Login as Staff, compare | - Admin sees all menus<br>- Staff sees limited items<br>- "Quản lý người dùng" hidden for staff<br>- "Cài đặt hệ thống" admin-only | Both roles available |
