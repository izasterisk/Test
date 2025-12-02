# Feature_Vendor - Vendor Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Vendor |
| **Test requirement** | API and design are available |
| **Number of TCs** | 14 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 14 | 0 |
| Round 2 | 0 | 0 | 14 | 0 |
| Round 3 | 0 | 0 | 14 | 0 |

---

## Test Cases

### Vendor Registration

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| VEND01 | Register as vendor | 1. Go to Vendor Registration page<br>2. Fill company info, contact details<br>3. Upload certificate PDFs<br>4. Submit form | - Vendor profile created (Pending)<br>- Certificates uploaded<br>- Status 201 Created | None |
| VEND02 | Register with missing certificates | 1. Go to Vendor Registration<br>2. Fill info but no certificate files<br>3. Submit | - Error: No certificate files provided<br>- Status 400 Bad Request | None |
| VEND03 | Register with existing email | 1. Go to Vendor Registration<br>2. Use already registered email<br>3. Submit | - Error: Email already exists<br>- Status 400 Bad Request | Email registered |

---

### Vendor Profile Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| VEND04 | Get all vendors | 1. Call GET `/api/VendorProfiles?page=1&pageSize=10` | - List of vendors returned<br>- Status 200 OK | Vendors exist |
| VEND05 | Get vendor by ID | 1. Call GET `/api/VendorProfiles/{id}` | - Vendor details returned<br>- Includes certificates | Vendor exists |
| VEND06 | Get vendor by user ID | 1. Call GET `/api/VendorProfiles/by-user/{userId}` | - Vendor profile returned | Vendor exists |
| VEND07 | Update vendor profile | 1. Login as Vendor<br>2. Call PUT `/api/VendorProfiles/{id}`<br>3. Update company info | - Profile updated<br>- Status 204 No Content | Logged in as Vendor |
| VEND08 | Get vendor with non-existent ID | 1. Call GET `/api/VendorProfiles/99999` | - Status 404 Not Found | None |

---

### Vendor Approval

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| VEND09 | Approve vendor (Admin/Staff) | 1. Login as Admin/Staff<br>2. Call POST `/api/VendorProfiles/{id}/approve`<br>3. Send approvedBy ID | - Vendor approved<br>- User verified<br>- Email sent<br>- Status 204 No Content | Pending vendor exists |
| VEND10 | Reject vendor with reason | 1. Login as Admin/Staff<br>2. Call POST `/api/VendorProfiles/{id}/reject`<br>3. Send rejection reason | - Vendor rejected<br>- Reason saved<br>- Email sent<br>- Status 204 No Content | Pending vendor exists |
| VEND11 | Reject without reason (not allowed) | 1. Login as Admin/Staff<br>2. Call POST `/api/VendorProfiles/{id}/reject`<br>3. No rejection reason | - Error: RejectionReason required<br>- Status 400 Bad Request | Pending vendor exists |

---

### Vendor Account

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| VEND12 | Soft delete vendor account | 1. Login as Admin<br>2. Call DELETE `/api/VendorProfiles/account/{userId}` | - User status = Inactive<br>- DeletedAt set<br>- Status 204 No Content | Vendor account exists |
| VEND13 | Hard delete vendor profile | 1. Login as Admin<br>2. Call DELETE `/api/VendorProfiles/{id}` | - Vendor profile deleted<br>- User remains<br>- Status 204 No Content | Vendor profile exists |
| VEND14 | Suspended vendor cannot login | 1. Suspend vendor account<br>2. Try to login | - Error: Account suspended<br>- Status 401 Unauthorized | Vendor suspended |
