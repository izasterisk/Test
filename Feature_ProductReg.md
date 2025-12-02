# Feature 14: Product Registration - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_ProductReg |
| **Feature** | Product Registration |
| **Module** | Vendor Product Listing, Product Submission |
| **Total Test Cases** | 14 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 14.1 Product Registration Form Layout

| TC ID | TC_PREG_001 |
|-------|------------|
| **Description** | Verify product registration form layout |
| **Pre-conditions** | User logged in as Vendor |
| **Procedure** | 1. Navigate to "Add New Product"<br>2. Observe the registration form |
| **Expected Results** | - Multi-section form displayed<br>- Sections: Basic Info, Pricing, Images, Details<br>- Progress indicator (if multi-step)<br>- Required fields marked with asterisk (*)<br>- Save Draft and Submit buttons |

| TC ID | TC_PREG_002 |
|-------|------------|
| **Description** | Verify basic info section fields |
| **Pre-conditions** | User on product registration form |
| **Procedure** | 1. Observe Basic Info section<br>2. Check available fields |
| **Expected Results** | - Product Name input<br>- Category dropdown<br>- Subcategory (dynamic based on category)<br>- Short Description textarea<br>- SKU/Product Code (optional) |

### 14.2 Product Images Upload

| TC ID | TC_PREG_003 |
|-------|------------|
| **Description** | Verify product image upload area |
| **Pre-conditions** | User on product registration form |
| **Procedure** | 1. Locate image upload section<br>2. Observe upload interface |
| **Expected Results** | - Drag-and-drop area visible<br>- "Click to upload" alternative<br>- Accepted formats shown (JPG, PNG)<br>- Max file size indicated (e.g., 5MB)<br>- Minimum images required noted |

| TC ID | TC_PREG_004 |
|-------|------------|
| **Description** | Verify single image upload |
| **Pre-conditions** | User on image upload section |
| **Procedure** | 1. Click upload area<br>2. Select a valid image (JPG, 2MB)<br>3. Observe upload process |
| **Expected Results** | - File dialog opens<br>- Upload progress indicator<br>- Image preview displayed<br>- Delete/Remove option on image<br>- Can upload more images |

| TC ID | TC_PREG_005 |
|-------|------------|
| **Description** | Verify multiple images upload |
| **Pre-conditions** | User on image upload section |
| **Procedure** | 1. Select 5 images at once<br>2. Observe upload and display |
| **Expected Results** | - All images upload simultaneously<br>- Progress shown for each<br>- Thumbnails displayed in grid<br>- Can reorder by drag (if supported)<br>- First image marked as primary |

| TC ID | TC_PREG_006 |
|-------|------------|
| **Description** | Verify image upload validation |
| **Pre-conditions** | User on image upload section |
| **Procedure** | 1. Try to upload PDF file<br>2. Try to upload 10MB image |
| **Expected Results** | - Invalid format: "Only JPG, PNG allowed"<br>- Oversized file: "File exceeds 5MB limit"<br>- Files rejected<br>- Valid files still accepted |

### 14.3 Pricing & Inventory

| TC ID | TC_PREG_007 |
|-------|------------|
| **Description** | Verify pricing section fields |
| **Pre-conditions** | User on product registration form |
| **Procedure** | 1. Navigate to Pricing section<br>2. Observe fields |
| **Expected Results** | - Price input with currency symbol<br>- Compare/Original price (for discounts)<br>- Unit selection (kg, piece, pack)<br>- Stock quantity input<br>- Low stock threshold (optional) |

| TC ID | TC_PREG_008 |
|-------|------------|
| **Description** | Verify price validation |
| **Pre-conditions** | User on pricing section |
| **Procedure** | 1. Enter price: -1000<br>2. Enter price: 0<br>3. Enter price: "abc" |
| **Expected Results** | - Negative price: "Price must be positive"<br>- Zero price: Warning or error<br>- Non-numeric: Input rejected or error<br>- Valid positive numbers accepted |

### 14.4 Product Details

| TC ID | TC_PREG_009 |
|-------|------------|
| **Description** | Verify product details section |
| **Pre-conditions** | User on product registration form |
| **Procedure** | 1. Navigate to Details section<br>2. Observe fields |
| **Expected Results** | - Full Description (rich text editor)<br>- Weight input<br>- Dimensions (optional)<br>- Origin/Source location<br>- Certifications selection (organic, etc.) |

| TC ID | TC_PREG_010 |
|-------|------------|
| **Description** | Verify rich text editor functionality |
| **Pre-conditions** | User on description field |
| **Procedure** | 1. Type text in description<br>2. Apply bold formatting<br>3. Create bullet list<br>4. Add a link |
| **Expected Results** | - Text formatting tools visible<br>- Bold, italic, underline work<br>- Lists can be created<br>- Links can be added<br>- Preview shows formatted text |

### 14.5 Form Submission

| TC ID | TC_PREG_011 |
|-------|------------|
| **Description** | Verify submit with valid complete data |
| **Pre-conditions** | User filled all required fields |
| **Procedure** | 1. Fill all required fields with valid data<br>2. Upload at least one image<br>3. Click "Submit for Review" |
| **Expected Results** | - Form validates all fields<br>- Loading indicator during submission<br>- Success: "Product submitted for review"<br>- Redirected to product list<br>- Status shows "Pending Review" |

| TC ID | TC_PREG_012 |
|-------|------------|
| **Description** | Verify submit with missing required fields |
| **Pre-conditions** | User on product registration form |
| **Procedure** | 1. Leave Product Name empty<br>2. Leave Price empty<br>3. Skip image upload<br>4. Click Submit |
| **Expected Results** | - Validation errors displayed<br>- "Product name is required"<br>- "Price is required"<br>- "At least one image required"<br>- Form scrolls to first error |

| TC ID | TC_PREG_013 |
|-------|------------|
| **Description** | Verify save as draft functionality |
| **Pre-conditions** | User partially filled form |
| **Procedure** | 1. Fill some fields (not all)<br>2. Click "Save as Draft" |
| **Expected Results** | - Draft saved successfully<br>- Toast: "Draft saved"<br>- Can navigate away safely<br>- Draft appears in product list<br>- Can resume editing later |

| TC ID | TC_PREG_014 |
|-------|------------|
| **Description** | Verify unsaved changes warning |
| **Pre-conditions** | User made changes to form |
| **Procedure** | 1. Edit product name<br>2. Try to navigate away without saving<br>3. Observe behavior |
| **Expected Results** | - Browser/App shows warning dialog<br>- "You have unsaved changes"<br>- Options: Stay, Leave (discard)<br>- Staying keeps form data |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 14 |
| Priority - High | 6 |
| Priority - Medium | 5 |
| Priority - Low | 3 |
