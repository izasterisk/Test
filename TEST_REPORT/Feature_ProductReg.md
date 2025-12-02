# Feature_ProductReg - Product Registration UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Product Registration |
| **Test requirement** | Vendor Product Listing, Submission pages available |
| **Number of TCs** | 14 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 14 | 0 |
| Round 2 | 0 | 0 | 14 | 0 |
| Round 3 | 0 | 0 | 14 | 0 |

---

## Test Cases

### Product Registration Form Layout

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PREG01 | View registration form | 1. Login as Vendor<br>2. Navigate to "Thêm sản phẩm" | - Multi-section form displays<br>- Sections: Thông tin cơ bản, Giá cả, Hình ảnh, Chi tiết<br>- Progress indicator (if multi-step)<br>- Required fields marked (*) | Logged in as Vendor |
| PREG02 | Basic info section | 1. On registration form<br>2. View basic info section | - Product Name input<br>- Category dropdown<br>- Subcategory (dynamic)<br>- Short Description<br>- SKU (optional) | Form open |

---

### Product Images Upload

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PREG03 | Image upload area | 1. On registration form<br>2. Locate image section | - Drag-and-drop area visible<br>- "Click để tải lên" option<br>- Formats: JPG, PNG shown<br>- Max size: 5MB noted<br>- Min images required | Form open |
| PREG04 | Upload single image | 1. On image section<br>2. Click upload area<br>3. Select valid JPG (2MB) | - File dialog opens<br>- Upload progress shows<br>- Preview displayed<br>- Delete option on image<br>- Can upload more | Form open |
| PREG05 | Upload multiple images | 1. On image section<br>2. Select 5 images at once | - All images upload<br>- Progress shown for each<br>- Thumbnails in grid<br>- Drag to reorder (if supported)<br>- First = primary image | Form open |
| PREG06 | Image validation | 1. On image section<br>2. Try upload PDF file<br>3. Try upload >5MB image | - Invalid format: "Chỉ chấp nhận JPG, PNG"<br>- Oversized: "File vượt quá 5MB"<br>- Files rejected<br>- Valid files accepted | Form open |

---

### Pricing & Inventory

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PREG07 | Pricing section fields | 1. On registration form<br>2. View pricing section | - Price input with ₫ symbol<br>- Compare/original price (discount)<br>- Unit selection (kg, cái, gói)<br>- Stock quantity input<br>- Low stock threshold | Form open |
| PREG08 | Price validation | 1. On pricing section<br>2. Enter price: -1000<br>3. Enter price: 0<br>4. Enter: "abc" | - Negative: "Giá phải > 0"<br>- Zero: Warning or error<br>- Non-numeric: Rejected<br>- Valid positive accepted | Form open |

---

### Product Details

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PREG09 | Details section fields | 1. On registration form<br>2. View details section | - Full Description (rich editor)<br>- Weight input<br>- Dimensions (optional)<br>- Origin/Source<br>- Certifications selection | Form open |
| PREG10 | Rich text editor | 1. On description field<br>2. Type text<br>3. Apply bold<br>4. Create bullet list | - Formatting tools visible<br>- Bold, italic work<br>- Lists created<br>- Links addable<br>- Preview shows formatted | Form open |

---

### Form Submission

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PREG11 | Submit with valid data | 1. Fill all required fields<br>2. Upload ≥1 image<br>3. Click "Gửi duyệt" | - Form validates all fields<br>- Loading shows<br>- Success "Sản phẩm đã gửi duyệt"<br>- Redirect to product list<br>- Status = "Chờ duyệt" | All fields valid |
| PREG12 | Submit missing fields | 1. Leave Product Name empty<br>2. Leave Price empty<br>3. Skip image upload<br>4. Click Submit | - Validation errors shown<br>- "Tên sản phẩm là bắt buộc"<br>- "Giá là bắt buộc"<br>- "Cần ít nhất 1 hình ảnh"<br>- Scroll to first error | Form open |
| PREG13 | Save as draft | 1. Fill some fields (not all)<br>2. Click "Lưu nháp" | - Draft saved<br>- Toast "Đã lưu nháp"<br>- Can navigate away<br>- Draft in product list<br>- Can resume editing | Form open |
| PREG14 | Unsaved changes warning | 1. Edit product name<br>2. Try navigate away without saving | - Warning dialog shows<br>- "Bạn có thay đổi chưa lưu"<br>- Options: Ở lại, Rời đi<br>- Stay keeps form data | Changes made |
