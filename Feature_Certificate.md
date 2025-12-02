# Feature_Certificate - Certificate UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Certificate |
| **Test requirement** | Certificate upload/management available |
| **Number of TCs** | 4 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 4 | 0 |
| Round 2 | 0 | 0 | 4 | 0 |
| Round 3 | 0 | 0 | 4 | 0 |

---

## Test Cases

### Certificate Upload (Vendor)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CERT01 | Upload vendor certificate | 1. Login as Vendor<br>2. Go to Vendor Profile/Certificates section<br>3. Click "Thêm chứng chỉ"<br>4. Fill: Certificate name, code<br>5. Upload PDF file<br>6. Click "Lưu" | - Upload form opens<br>- PDF file accepted<br>- Loading during upload<br>- Success toast "Tải lên chứng chỉ thành công"<br>- Certificate shows in list (Pending) | Logged in as Vendor |
| CERT02 | Upload invalid file type | 1. Go to certificate upload<br>2. Try to upload a .txt or .exe file | - File rejected<br>- Error message "Chỉ chấp nhận file PDF"<br>- Form not submitted | Logged in as Vendor |

---

### Certificate Management (Vendor View)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CERT03 | View certificate list | 1. Login as Vendor<br>2. Navigate to Certificates section | - Certificate list displays<br>- Shows: name, code, status badge<br>- Status: Pending, Approved, Rejected<br>- Can view PDF | Logged in as Vendor |
| CERT04 | View certificate approval status | 1. Go to certificate list<br>2. Check status of certificates | - Pending: Yellow badge<br>- Approved: Green badge with date<br>- Rejected: Red badge with reason<br>- Can download/view PDF | Has certificates |
