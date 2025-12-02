# Feature 15: Certificates Management - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_Certificate |
| **Feature** | Certificates Management |
| **Module** | Product & Vendor Certificates |
| **Total Test Cases** | 12 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 15.1 Certificate List View

| TC ID | TC_CERT_001 |
|-------|------------|
| **Description** | Verify vendor certificates list page |
| **Pre-conditions** | User logged in as Vendor |
| **Procedure** | 1. Navigate to "My Certificates" or similar<br>2. Observe the certificates list |
| **Expected Results** | - Page displays list of certificates<br>- Each entry: Certificate Name, Type, Issue Date, Expiry, Status<br>- Status badges (Active, Expired, Pending)<br>- "Upload Certificate" button visible |

| TC ID | TC_CERT_002 |
|-------|------------|
| **Description** | Verify empty certificates state |
| **Pre-conditions** | Vendor has no certificates |
| **Procedure** | 1. Navigate to certificates list<br>2. Observe empty state |
| **Expected Results** | - Empty state message displayed<br>- "No certificates uploaded yet"<br>- "Upload Your First Certificate" CTA<br>- Info about why certificates matter |

| TC ID | TC_CERT_003 |
|-------|------------|
| **Description** | Verify certificate status filter |
| **Pre-conditions** | Vendor has multiple certificates |
| **Procedure** | 1. Click status filter dropdown<br>2. Select "Active" certificates<br>3. Observe filtered results |
| **Expected Results** | - Filter options: All, Active, Pending, Expired, Rejected<br>- List filters to selected status<br>- Count updates accordingly<br>- Clear filter option |

### 15.2 Upload Certificate

| TC ID | TC_CERT_004 |
|-------|------------|
| **Description** | Verify upload certificate form |
| **Pre-conditions** | User on certificates page |
| **Procedure** | 1. Click "Upload Certificate" button<br>2. Observe the upload form/modal |
| **Expected Results** | - Modal or page opens with form<br>- Fields: Certificate Type dropdown, Certificate Name<br>- File upload area<br>- Issue Date and Expiry Date pickers<br>- Submit and Cancel buttons |

| TC ID | TC_CERT_005 |
|-------|------------|
| **Description** | Verify certificate upload with valid data |
| **Pre-conditions** | User on certificate upload form |
| **Procedure** | 1. Select Type: "Organic Certification"<br>2. Enter Name: "USDA Organic 2024"<br>3. Upload PDF file (valid certificate)<br>4. Set Issue Date: Jan 1, 2024<br>5. Set Expiry Date: Dec 31, 2024<br>6. Click "Submit" |
| **Expected Results** | - Form validates successfully<br>- File uploads with progress<br>- Success: "Certificate uploaded for review"<br>- Certificate appears in list with "Pending" status<br>- Email confirmation (if applicable) |

| TC ID | TC_CERT_006 |
|-------|------------|
| **Description** | Verify certificate upload - validation errors |
| **Pre-conditions** | User on certificate upload form |
| **Procedure** | 1. Leave all fields empty<br>2. Click "Submit" |
| **Expected Results** | - Validation errors inline<br>- "Certificate type is required"<br>- "Please upload certificate file"<br>- "Issue date is required"<br>- Form does not submit |

| TC ID | TC_CERT_007 |
|-------|------------|
| **Description** | Verify certificate file type validation |
| **Pre-conditions** | User on certificate upload form |
| **Procedure** | 1. Fill required fields<br>2. Try to upload .exe file<br>3. Try to upload .txt file |
| **Expected Results** | - Invalid format error displayed<br>- "Only PDF, JPG, PNG files accepted"<br>- Malicious file types blocked<br>- Valid formats accepted |

| TC ID | TC_CERT_008 |
|-------|------------|
| **Description** | Verify expiry date validation |
| **Pre-conditions** | User on certificate upload form |
| **Procedure** | 1. Set Issue Date: Jan 1, 2024<br>2. Set Expiry Date: Dec 31, 2023 (before issue)<br>3. Try to submit |
| **Expected Results** | - Validation error: "Expiry date must be after issue date"<br>- Form does not submit<br>- Date fields highlighted |

### 15.3 Certificate Detail View

| TC ID | TC_CERT_009 |
|-------|------------|
| **Description** | Verify certificate detail view |
| **Pre-conditions** | Vendor has uploaded certificates |
| **Procedure** | 1. Click on a certificate from list<br>2. Observe detail view |
| **Expected Results** | - Full certificate information displayed<br>- Preview of uploaded document (if image/PDF)<br>- Download original file option<br>- Status with timestamp<br>- Admin notes (if rejected) |

| TC ID | TC_CERT_010 |
|-------|------------|
| **Description** | Verify download certificate file |
| **Pre-conditions** | Viewing certificate detail |
| **Procedure** | 1. Click "Download" button<br>2. Observe download behavior |
| **Expected Results** | - File download initiates<br>- Original filename preserved<br>- Correct file format downloaded<br>- File opens correctly |

### 15.4 Certificate Status & Expiry

| TC ID | TC_CERT_011 |
|-------|------------|
| **Description** | Verify expiring soon warning |
| **Pre-conditions** | Certificate expiring within 30 days |
| **Procedure** | 1. View certificates list<br>2. Observe expiring certificate |
| **Expected Results** | - Warning indicator on expiring certificates<br>- "Expiring in X days" message<br>- Orange/yellow warning color<br>- Renewal prompt or link |

| TC ID | TC_CERT_012 |
|-------|------------|
| **Description** | Verify expired certificate display |
| **Pre-conditions** | Certificate has expired |
| **Procedure** | 1. View certificates list<br>2. Observe expired certificate |
| **Expected Results** | - "Expired" status badge (red)<br>- Expiry date clearly shown<br>- "Renew" or "Upload New" option<br>- May affect product visibility warning |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 12 |
| Priority - High | 5 |
| Priority - Medium | 5 |
| Priority - Low | 2 |
