# Feature_Certificate - Certificates Management UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Certificates Management |
| **Test requirement** | Product & Vendor Certificates pages available |
| **Number of TCs** | 12 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 12 | 0 |
| Round 2 | 0 | 0 | 12 | 0 |
| Round 3 | 0 | 0 | 12 | 0 |

---

## Test Cases

### Certificate List View

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CERT01 | View certificates list | 1. Login as Vendor<br>2. Navigate to "Chứng chỉ" | - Certificate list displays<br>- Columns: Name, Type, Issue Date, Expiry, Status<br>- Status badges (Active, Expired, Pending)<br>- "Tải lên chứng chỉ" button | Logged in as Vendor |
| CERT02 | Empty certificates state | 1. Login (no certificates)<br>2. Navigate to certificates | - Empty state message<br>- "Bạn chưa có chứng chỉ nào"<br>- "Tải lên chứng chỉ đầu tiên" button<br>- Info about certificate benefits | No certificates |
| CERT03 | Filter by status | 1. On certificates list<br>2. Click status filter<br>3. Select "Còn hiệu lực" | - Filter: Tất cả, Còn hiệu lực, Chờ duyệt, Hết hạn, Từ chối<br>- List filters accordingly<br>- Count updates<br>- Clear filter option | Has certificates |

---

### Upload Certificate

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CERT04 | View upload form | 1. On certificates page<br>2. Click "Tải lên chứng chỉ" | - Modal/page opens<br>- Fields: Type dropdown, Name, File upload<br>- Issue Date and Expiry Date pickers<br>- Gửi and Hủy buttons | Logged in |
| CERT05 | Upload valid certificate | 1. Open upload form<br>2. Select Type: "Chứng nhận hữu cơ"<br>3. Enter Name: "USDA Organic 2024"<br>4. Upload PDF file<br>5. Set Issue: Jan 1, 2024<br>6. Set Expiry: Dec 31, 2024<br>7. Click "Gửi" | - Form validates<br>- File uploads with progress<br>- Success "Chứng chỉ đã gửi duyệt"<br>- Certificate in list (Pending)<br>- Email confirmation | Form open |
| CERT06 | Upload - validation errors | 1. Open upload form<br>2. Leave all fields empty<br>3. Click "Gửi" | - Inline errors shown<br>- "Loại chứng chỉ là bắt buộc"<br>- "Vui lòng tải lên file"<br>- "Ngày cấp là bắt buộc"<br>- Form not submitted | Form open |
| CERT07 | File type validation | 1. Open upload form<br>2. Fill required fields<br>3. Try upload .exe file | - Error "Chỉ chấp nhận PDF, JPG, PNG"<br>- Malicious files blocked<br>- Valid formats accepted | Form open |
| CERT08 | Expiry date validation | 1. Open upload form<br>2. Set Issue: Jan 1, 2024<br>3. Set Expiry: Dec 31, 2023 (before issue)<br>4. Try submit | - Error "Ngày hết hạn phải sau ngày cấp"<br>- Form not submitted<br>- Date fields highlighted | Form open |

---

### Certificate Detail View

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CERT09 | View certificate detail | 1. On certificates list<br>2. Click a certificate | - Full information displayed<br>- Preview (if image/PDF)<br>- Download original option<br>- Status with timestamp<br>- Admin notes (if rejected) | Certificate exists |
| CERT10 | Download certificate file | 1. On certificate detail<br>2. Click "Tải xuống" | - File download starts<br>- Original filename<br>- Correct format<br>- File opens correctly | Certificate exists |

---

### Certificate Status & Expiry

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CERT11 | Expiring soon warning | 1. View certificates list<br>2. Observe expiring certificate | - Warning indicator shown<br>- "Còn X ngày" message<br>- Orange/yellow color<br>- Renewal prompt/link | Certificate expiring |
| CERT12 | Expired certificate display | 1. View certificates list<br>2. Observe expired certificate | - "Hết hạn" badge (red)<br>- Expiry date shown<br>- "Gia hạn" or "Tải lên mới" option<br>- Product visibility warning | Certificate expired |
