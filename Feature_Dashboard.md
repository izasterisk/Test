# Feature_Dashboard - Dashboard Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Dashboard |
| **Test requirement** | API and design are available |
| **Number of TCs** | 8 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 8 | 0 |
| Round 2 | 0 | 0 | 8 | 0 |
| Round 3 | 0 | 0 | 8 | 0 |

---

## Test Cases

### Revenue Statistics

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH01 | Get revenue by time range | 1. Login as Admin/Staff<br>2. Call GET `/api/Dashboard/revenue?from=2024-01-01&to=2024-12-31` | - Total revenue returned<br>- Status 200 OK | Logged in as Admin/Staff |
| DASH02 | Get revenue last 7 days | 1. Login as Admin/Staff<br>2. Call GET `/api/Dashboard/revenue/last-7-days` | - Daily revenue for 7 days<br>- Includes today<br>- Status 200 OK | Logged in as Admin/Staff |
| DASH03 | Get revenue with invalid date range | 1. Login as Admin/Staff<br>2. Call GET `/api/Dashboard/revenue?from=2024-12-31&to=2024-01-01` | - Error or empty result<br>- Handled gracefully | Logged in as Admin/Staff |

---

### Order Statistics

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH04 | Get order statistics by time range | 1. Login as Admin/Staff<br>2. Call GET `/api/Dashboard/orders?from=2024-01-01&to=2024-12-31` | - Order counts by status<br>- Paid, Shipped, Delivered, Cancelled, Refunded<br>- Status 200 OK | Logged in as Admin/Staff |
| DASH05 | Get order statistics with no data | 1. Login as Admin/Staff<br>2. Query date range with no orders | - Zero counts returned<br>- Status 200 OK | Logged in as Admin/Staff |

---

### Queue Statistics

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH06 | Get queue statistics | 1. Login as Admin/Staff<br>2. Call GET `/api/Dashboard/queues` | - Pending counts for:<br>  • Unverified vendors<br>  • Product registrations<br>  • Certificates<br>  • Requests<br>- Status 200 OK | Logged in as Admin/Staff |

---

### Authorization

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| DASH07 | Customer access dashboard | 1. Login as Customer<br>2. Call GET `/api/Dashboard/revenue` | - Error: Access denied<br>- Status 403 Forbidden | Logged in as Customer |
| DASH08 | Unauthenticated access dashboard | 1. No login<br>2. Call GET `/api/Dashboard/queues` | - Error: Unauthorized<br>- Status 401 Unauthorized | Not logged in |
