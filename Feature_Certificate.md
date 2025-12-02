# Feature_Certificate - Certificate Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Certificate |
| **Test requirement** | API and design are available |
| **Number of TCs** | 12 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 12 | 0 |
| Round 2 | 0 | 0 | 12 | 0 |
| Round 3 | 0 | 0 | 12 | 0 |

---

## Test Cases

### Product Certificate

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CERT01 | Create product certificate | 1. Call POST `/api/ProductCertificate` (multipart)<br>2. Upload PDF file, code, name | - Certificate created (Pending)<br>- PDF uploaded<br>- Status 201 Created | Product exists |
| CERT02 | Create multiple certificates (batch) | 1. Call POST `/api/ProductCertificate/upload`<br>2. Send arrays: CertificationCode[], CertificationName[], Files[] | - All certificates created<br>- Status 201 Created | Product exists |
| CERT03 | Get certificates by product ID | 1. Call GET `/api/ProductCertificate/by-product/{productId}` | - List of product's certificates<br>- Status 200 OK | Product has certificates |
| CERT04 | Update product certificate | 1. Call PUT `/api/ProductCertificate/{id}` (multipart)<br>2. Update name, add/remove files | - Certificate updated<br>- Status 200 OK | Certificate exists |
| CERT05 | Approve product certificate | 1. Login as Admin/Staff<br>2. Call PATCH `/api/ProductCertificate/status/{id}`<br>3. Send status=Approved | - Certificate approved<br>- Status 204 No Content | Pending certificate |
| CERT06 | Reject product certificate | 1. Login as Admin/Staff<br>2. Call PATCH `/api/ProductCertificate/status/{id}`<br>3. Send status=Rejected, rejectionReason | - Certificate rejected<br>- Reason saved<br>- Status 204 No Content | Pending certificate |

---

### Vendor Certificate

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CERT07 | Create vendor certificate | 1. Call POST `/api/VendorCertificate` (multipart)<br>2. Upload PDF files, codes[], names[] | - Certificate created<br>- Status 200 OK | Vendor exists |
| CERT08 | Get certificates by vendor ID | 1. Call GET `/api/VendorCertificate/vendor/{vendorId}` | - List of vendor's certificates<br>- Status 200 OK | Vendor has certificates |
| CERT09 | Get certificate by ID | 1. Call GET `/api/VendorCertificate/{id}` | - Certificate details<br>- Includes verification info<br>- Status 200 OK | Certificate exists |
| CERT10 | Update vendor certificate | 1. Call PUT `/api/VendorCertificate/{id}` (multipart)<br>2. Add new files, remove old | - Certificate updated<br>- Status 200 OK | Certificate exists |
| CERT11 | Change certificate status | 1. Login as Admin/Staff<br>2. Call PATCH `/api/VendorCertificate/{id}/change-status`<br>3. Send status, verifiedBy | - Status updated<br>- Status 200 OK | Certificate exists |
| CERT12 | Delete vendor certificate | 1. Call DELETE `/api/VendorCertificate/{id}` | - Certificate deleted<br>- Status 204 No Content | Certificate exists |
