# Feature 6: Vendor Management - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_Vendor |
| **Feature** | Vendor Management |
| **Module** | Vendor Dashboard, Profile & Registration |
| **Total Test Cases** | 16 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 6.1 Vendor Registration

| TC ID | TC_VEN_001 |
|-------|------------|
| **Description** | Verify vendor registration page layout |
| **Pre-conditions** | User logged in as regular user (not vendor) |
| **Procedure** | 1. Navigate to "Become a Vendor" page<br>2. Observe the registration form layout |
| **Expected Results** | - Registration form displays with clear sections<br>- Required fields: Business Name, Tax ID, Description, Address<br>- Terms and conditions checkbox visible<br>- Submit button at bottom |

| TC ID | TC_VEN_002 |
|-------|------------|
| **Description** | Verify vendor registration with valid data |
| **Pre-conditions** | User on vendor registration page |
| **Procedure** | 1. Enter Business Name: "Green Farm Co"<br>2. Enter Tax ID: "1234567890"<br>3. Enter business description<br>4. Fill address information<br>5. Check terms agreement<br>6. Click "Register as Vendor" |
| **Expected Results** | - Form validates all fields<br>- Loading state during submission<br>- Success: "Registration submitted for review"<br>- Redirected to pending approval page |

| TC ID | TC_VEN_003 |
|-------|------------|
| **Description** | Verify vendor registration - missing required fields |
| **Pre-conditions** | User on vendor registration page |
| **Procedure** | 1. Leave Business Name empty<br>2. Leave Tax ID empty<br>3. Click submit button |
| **Expected Results** | - Validation errors appear inline<br>- "Business name is required"<br>- "Tax ID is required"<br>- Form does not submit<br>- Error fields highlighted in red |

| TC ID | TC_VEN_004 |
|-------|------------|
| **Description** | Verify vendor registration - invalid Tax ID format |
| **Pre-conditions** | User on vendor registration page |
| **Procedure** | 1. Fill required fields<br>2. Enter Tax ID: "abc123" (invalid)<br>3. Click submit |
| **Expected Results** | - Validation error: "Invalid Tax ID format"<br>- Tooltip or help text shows valid format<br>- Form does not submit |

### 6.2 Vendor Dashboard

| TC ID | TC_VEN_005 |
|-------|------------|
| **Description** | Verify Vendor Dashboard main layout |
| **Pre-conditions** | User logged in as approved Vendor |
| **Procedure** | 1. Navigate to Vendor Dashboard<br>2. Observe the main dashboard page |
| **Expected Results** | - Dashboard header shows vendor business name<br>- Stats cards: Total Products, Orders, Revenue, Rating<br>- Recent orders section visible<br>- Quick action buttons available |

| TC ID | TC_VEN_006 |
|-------|------------|
| **Description** | Verify Vendor sidebar navigation |
| **Pre-conditions** | User on Vendor Dashboard |
| **Procedure** | 1. Observe left sidebar menu<br>2. Click on each menu item<br>3. Verify navigation works |
| **Expected Results** | - Sidebar shows: Dashboard, Products, Orders, Profile, Wallet, Settings<br>- Active menu item highlighted<br>- Click navigates to correct page<br>- Sidebar can collapse on mobile |

| TC ID | TC_VEN_007 |
|-------|------------|
| **Description** | Verify dashboard stats cards update correctly |
| **Pre-conditions** | Vendor has products and orders |
| **Procedure** | 1. View dashboard stats<br>2. Note current values<br>3. Complete an order in another tab<br>4. Refresh dashboard |
| **Expected Results** | - Stats cards show real data<br>- Numbers formatted correctly (currency, counts)<br>- Refresh updates values<br>- Loading skeleton while fetching |

### 6.3 Vendor Profile Management

| TC ID | TC_VEN_008 |
|-------|------------|
| **Description** | Verify vendor profile view page |
| **Pre-conditions** | User logged in as Vendor |
| **Procedure** | 1. Navigate to Vendor Profile page<br>2. Observe profile information |
| **Expected Results** | - Profile shows: Business Name, Logo, Description<br>- Contact information displayed<br>- Address information visible<br>- Rating and review count shown<br>- "Edit Profile" button available |

| TC ID | TC_VEN_009 |
|-------|------------|
| **Description** | Verify vendor profile edit functionality |
| **Pre-conditions** | User on Vendor Profile page |
| **Procedure** | 1. Click "Edit Profile" button<br>2. Edit form opens<br>3. Change business description<br>4. Click "Save Changes" |
| **Expected Results** | - Edit modal/page opens with current data<br>- Fields are editable<br>- Validation on required fields<br>- Success toast: "Profile updated"<br>- Profile reflects changes |

| TC ID | TC_VEN_010 |
|-------|------------|
| **Description** | Verify vendor logo upload |
| **Pre-conditions** | User on Vendor Profile edit |
| **Procedure** | 1. Click on logo upload area<br>2. Select valid image (PNG, 500x500, 1MB)<br>3. Observe preview<br>4. Save changes |
| **Expected Results** | - File dialog opens<br>- Preview shows selected image<br>- Upload progress indicator<br>- Success: Logo updated on profile<br>- Old logo replaced |

| TC ID | TC_VEN_011 |
|-------|------------|
| **Description** | Verify vendor logo upload - invalid file |
| **Pre-conditions** | User on Vendor Profile edit |
| **Procedure** | 1. Click logo upload<br>2. Select invalid file (PDF or >5MB image)<br>3. Observe error |
| **Expected Results** | - Error: "Invalid file type" or "File too large"<br>- Upload rejected<br>- Supported formats and size limit shown |

### 6.4 Vendor Products Management

| TC ID | TC_VEN_012 |
|-------|------------|
| **Description** | Verify vendor products list page |
| **Pre-conditions** | Vendor has products listed |
| **Procedure** | 1. Navigate to "My Products" from vendor dashboard<br>2. Observe products table |
| **Expected Results** | - Table shows vendor's products only<br>- Columns: Image, Name, Price, Stock, Status, Actions<br>- "Add Product" button visible<br>- Search and filter available |

| TC ID | TC_VEN_013 |
|-------|------------|
| **Description** | Verify add new product button navigation |
| **Pre-conditions** | User on vendor products page |
| **Procedure** | 1. Click "Add Product" button<br>2. Observe navigation/modal |
| **Expected Results** | - Navigates to product registration form<br>- Or opens product creation modal<br>- Form ready for input |

| TC ID | TC_VEN_014 |
|-------|------------|
| **Description** | Verify product status toggle |
| **Pre-conditions** | Vendor has active products |
| **Procedure** | 1. Find an active product in list<br>2. Click status toggle or "Deactivate" button<br>3. Confirm action if prompted |
| **Expected Results** | - Confirmation dialog appears<br>- After confirm: Status changes to "Inactive"<br>- Toast: "Product deactivated"<br>- Product hidden from marketplace |

### 6.5 Vendor Orders

| TC ID | TC_VEN_015 |
|-------|------------|
| **Description** | Verify vendor orders list |
| **Pre-conditions** | Vendor has received orders |
| **Procedure** | 1. Navigate to "Orders" from vendor dashboard<br>2. View orders list |
| **Expected Results** | - Shows orders containing vendor's products<br>- Columns: Order ID, Customer, Items, Total, Status, Date<br>- Filter by status available<br>- Click row shows order details |

| TC ID | TC_VEN_016 |
|-------|------------|
| **Description** | Verify vendor order detail view |
| **Pre-conditions** | Vendor has orders |
| **Procedure** | 1. Click on an order row to view details<br>2. Observe order detail page/modal |
| **Expected Results** | - Shows ordered items with quantities<br>- Customer shipping address (partial for privacy)<br>- Order timeline/history<br>- Status update options if applicable<br>- Print/Export option available |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 16 |
| Priority - High | 7 |
| Priority - Medium | 6 |
| Priority - Low | 3 |
