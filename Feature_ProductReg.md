# Feature_ProductReg - Product Registration Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Product Registration |
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

### Create Registration

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PREG01 | Create product registration | 1. Login as Vendor<br>2. Call POST `/api/ProductRegistrations` (multipart)<br>3. Upload images, manual PDF, certificates | - Registration created (Pending)<br>- Files uploaded<br>- Status 200 OK | Logged in as Vendor |
| PREG02 | Create registration with invalid certificate | 1. Login as Vendor<br>2. Upload non-PDF certificate file | - Error: Only PDF accepted<br>- Status 400 Bad Request | Logged in as Vendor |
| PREG03 | Create registration without images | 1. Login as Vendor<br>2. Submit without product images | - Error or warning<br>- Validation message | Logged in as Vendor |

---

### View Registrations

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PREG04 | Get all registrations | 1. Call GET `/api/ProductRegistrations?page=1&pageSize=20` | - List of registrations<br>- Includes images, certificates<br>- Status 200 OK | Registrations exist |
| PREG05 | Get registration by ID | 1. Call GET `/api/ProductRegistrations/{id}` | - Registration details<br>- Full specifications<br>- Status 200 OK | Registration exists |
| PREG06 | Get registrations by vendor | 1. Call GET `/api/ProductRegistrations/vendor/{vendorId}` | - Only vendor's registrations<br>- Status 200 OK | Vendor has registrations |

---

### Update & Approval

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PREG07 | Update product registration | 1. Login as Vendor<br>2. Call PUT `/api/ProductRegistrations/{id}`<br>3. Update info, add/remove images | - Registration updated<br>- Status 200 OK | Own registration (Pending) |
| PREG08 | Approve registration | 1. Login as Admin/Staff<br>2. Call PATCH `/api/ProductRegistrations/{id}/status`<br>3. Send status=Approved | - Registration approved<br>- Product created automatically<br>- Media copied<br>- Status 204 No Content | Pending registration |
| PREG09 | Reject registration with reason | 1. Login as Admin/Staff<br>2. Call PATCH `/api/ProductRegistrations/{id}/status`<br>3. Send status=Rejected, rejectionReason | - Registration rejected<br>- Reason saved<br>- Status 204 No Content | Pending registration |
| PREG10 | Delete registration | 1. Login as Vendor<br>2. Call DELETE `/api/ProductRegistrations/{id}` | - Registration deleted<br>- Status 204 No Content | Own registration exists |
