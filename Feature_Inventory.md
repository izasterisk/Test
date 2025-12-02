# Feature 5: Inventory Management - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_Inventory |
| **Feature** | Inventory Management |
| **Module** | Admin/Staff Panel - Batch & Export Inventory |
| **Total Test Cases** | 14 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 5.1 Batch Inventory List

| TC ID | TC_INV_001 |
|-------|------------|
| **Description** | Verify Batch Inventory page displays correctly |
| **Pre-conditions** | User logged in as Admin/Staff |
| **Procedure** | 1. Navigate to Inventory Management<br>2. Click on "Batch Inventory" menu<br>3. Observe the page layout |
| **Expected Results** | - Page displays batch inventory table<br>- Table shows columns: ID, Product, Quantity, Import Date, Expiry, Status<br>- Pagination controls visible<br>- Search and filter options available |

| TC ID | TC_INV_002 |
|-------|------------|
| **Description** | Verify batch inventory search functionality |
| **Pre-conditions** | User on Batch Inventory page, data exists |
| **Procedure** | 1. Locate the search input field<br>2. Type a product name or batch ID<br>3. Press Enter or click search button |
| **Expected Results** | - Search results update in real-time<br>- Table filters to show matching batches only<br>- "No results found" message if no match<br>- Clear search restores full list |

| TC ID | TC_INV_003 |
|-------|------------|
| **Description** | Verify filter by status functionality |
| **Pre-conditions** | User on Batch Inventory page |
| **Procedure** | 1. Click on Status filter dropdown<br>2. Select "Active" status<br>3. Observe filtered results<br>4. Select "Expired" status |
| **Expected Results** | - Filter dropdown shows all status options<br>- Table updates to show only selected status<br>- Count indicator shows filtered results<br>- Filter can be cleared |

### 5.2 Create New Batch

| TC ID | TC_INV_004 |
|-------|------------|
| **Description** | Verify Create Batch form displays correctly |
| **Pre-conditions** | User on Batch Inventory page as Admin/Staff |
| **Procedure** | 1. Click "Add New Batch" or "+" button<br>2. Observe the form/modal that appears |
| **Expected Results** | - Form modal opens with animation<br>- Required fields marked with asterisk (*)<br>- Fields: Product select, Quantity, Import Date, Expiry Date, Notes<br>- Save and Cancel buttons visible |

| TC ID | TC_INV_005 |
|-------|------------|
| **Description** | Verify batch creation with valid data |
| **Pre-conditions** | Create Batch form is open |
| **Procedure** | 1. Select a product from dropdown<br>2. Enter quantity: 100<br>3. Select import date: today<br>4. Select expiry date: 6 months from now<br>5. Click "Save" button |
| **Expected Results** | - Form validates successfully<br>- Loading indicator during submission<br>- Success toast: "Batch created successfully"<br>- Modal closes<br>- New batch appears in table |

| TC ID | TC_INV_006 |
|-------|------------|
| **Description** | Verify batch creation validation - empty fields |
| **Pre-conditions** | Create Batch form is open |
| **Procedure** | 1. Leave all fields empty<br>2. Click "Save" button |
| **Expected Results** | - Form shows validation errors<br>- Product field: "Product is required"<br>- Quantity field: "Quantity is required"<br>- Import Date: "Import date is required"<br>- Save button disabled or form not submitted |

| TC ID | TC_INV_007 |
|-------|------------|
| **Description** | Verify batch creation - invalid quantity |
| **Pre-conditions** | Create Batch form is open |
| **Procedure** | 1. Select a product<br>2. Enter quantity: -50<br>3. Try to submit |
| **Expected Results** | - Validation error: "Quantity must be positive"<br>- Form does not submit<br>- Error highlighted on quantity field |

### 5.3 Edit Batch

| TC ID | TC_INV_008 |
|-------|------------|
| **Description** | Verify edit batch functionality |
| **Pre-conditions** | Batch inventory list has data |
| **Procedure** | 1. Click edit icon/button on a batch row<br>2. Edit form opens with pre-filled data<br>3. Modify quantity from 100 to 150<br>4. Click "Update" button |
| **Expected Results** | - Edit form shows current batch data<br>- Fields are editable<br>- Success toast: "Batch updated successfully"<br>- Table reflects updated quantity |

### 5.4 Export Inventory

| TC ID | TC_INV_009 |
|-------|------------|
| **Description** | Verify Export Inventory page layout |
| **Pre-conditions** | User logged in as Admin/Staff |
| **Procedure** | 1. Navigate to Inventory Management<br>2. Click on "Export Inventory" menu<br>3. Observe the page |
| **Expected Results** | - Page displays export history table<br>- Columns: ID, Product, Quantity, Export Date, Destination, Status<br>- "New Export" button visible<br>- Filter and search options available |

| TC ID | TC_INV_010 |
|-------|------------|
| **Description** | Verify create export record with valid data |
| **Pre-conditions** | User on Export Inventory page |
| **Procedure** | 1. Click "New Export" button<br>2. Select product from available batches<br>3. Enter export quantity: 50<br>4. Enter destination/reason<br>5. Click "Confirm Export" |
| **Expected Results** | - Modal form opens<br>- Batch selection shows available quantity<br>- Export quantity validated against available<br>- Success: "Export recorded successfully"<br>- Batch quantity updated |

| TC ID | TC_INV_011 |
|-------|------------|
| **Description** | Verify export validation - exceeds available quantity |
| **Pre-conditions** | Export form open, batch has 100 units |
| **Procedure** | 1. Select batch with 100 available units<br>2. Enter export quantity: 150<br>3. Try to submit |
| **Expected Results** | - Validation error: "Export quantity exceeds available (100)"<br>- Form does not submit<br>- Available quantity displayed for reference |

### 5.5 Inventory Reports

| TC ID | TC_INV_012 |
|-------|------------|
| **Description** | Verify inventory low stock warning display |
| **Pre-conditions** | Some products have low stock |
| **Procedure** | 1. Navigate to Inventory dashboard<br>2. Look for low stock indicators |
| **Expected Results** | - Low stock items highlighted in red/orange<br>- Warning badge shows count of low stock items<br>- Tooltip shows threshold information<br>- Click navigates to low stock filter |

| TC ID | TC_INV_013 |
|-------|------------|
| **Description** | Verify expiring soon filter functionality |
| **Pre-conditions** | Some batches expiring within 30 days |
| **Procedure** | 1. Click "Expiring Soon" filter/tab<br>2. Observe filtered results |
| **Expected Results** | - Table shows only batches expiring within threshold<br>- Expiry date highlighted in warning color<br>- Days until expiry calculated and shown<br>- Can export list for review |

| TC ID | TC_INV_014 |
|-------|------------|
| **Description** | Verify pagination in batch inventory table |
| **Pre-conditions** | More than 10 batch records exist |
| **Procedure** | 1. Observe pagination controls at table bottom<br>2. Click page 2<br>3. Click "Next" button<br>4. Change items per page to 25 |
| **Expected Results** | - Pagination shows current page and total<br>- Navigation buttons work correctly<br>- Items per page selector functions<br>- Table updates without full page reload |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 14 |
| Priority - High | 6 |
| Priority - Medium | 6 |
| Priority - Low | 2 |
