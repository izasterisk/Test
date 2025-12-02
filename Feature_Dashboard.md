# Feature_Dashboard - Dashboard UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Dashboard |
| **Test requirement** | Admin/Staff dashboard pages available |
| **Number of TCs** | 4 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 4 | 0 |
| Round 2 | 0 | 0 | 4 | 0 |
| Round 3 | 0 | 0 | 4 | 0 |

---

## Test Cases

### Admin Dashboard (/admin)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH01 | View admin dashboard | 1. Login as Admin<br>2. Navigate to /admin | - Dashboard page loads<br>- Overview stats cards visible<br>- Charts/graphs display<br>- Sidebar navigation works<br>- Recent activity section | Logged in as Admin |
| DASH02 | Navigate admin panels | 1. On Admin dashboard<br>2. Click "Quản lý người dùng" in sidebar<br>3. Click "Quản lý sản phẩm"<br>4. Click "Quản lý đơn hàng" | - Each panel loads correctly<br>- Active menu highlighted<br>- Panel content changes<br>- Breadcrumb updates (if any) | Logged in as Admin |

---

### Staff Dashboard (/staff)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH03 | View staff dashboard | 1. Login as Staff<br>2. Navigate to /staff | - Dashboard page loads<br>- Assigned tasks/stats shown<br>- Limited menu compared to Admin<br>- Can access allowed panels only | Logged in as Staff |
| DASH04 | Access unauthorized admin page | 1. Login as Staff<br>2. Try to access /admin directly | - Access denied or redirect<br>- Error message or redirect to /staff<br>- Cannot see admin-only features | Logged in as Staff |
