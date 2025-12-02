# Feature_ProductReg - Product Registration UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Product Registration |
| **Test requirement** | Vendor product registration page available |
| **Number of TCs** | 5 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 5 | 0 |
| Round 2 | 0 | 0 | 5 | 0 |
| Round 3 | 0 | 0 | 5 | 0 |

---

## Test Cases

### Register Product Page (/vendor/register-product)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PREG01 | Register new product | 1. Login as Vendor<br>2. Navigate to Register Product page<br>3. Fill form:<br>- Product name<br>- Category<br>- Price<br>- Description<br>- Upload images<br>4. Click "Đăng ký" | - Form displays all fields<br>- Category dropdown works<br>- Image upload shows preview<br>- Loading on submit<br>- Success toast "Đăng ký sản phẩm thành công"<br>- Product status = Pending | Logged in as Vendor |
| PREG02 | Register product with missing fields | 1. Go to register product page<br>2. Leave product name empty<br>3. Click "Đăng ký" | - Validation errors show<br>- Required fields highlighted<br>- "Tên sản phẩm không được để trống"<br>- Form not submitted | Logged in as Vendor |
| PREG03 | Upload multiple product images | 1. Go to register product page<br>2. Click image upload area<br>3. Select 3-5 images<br>4. View previews | - Multiple images can be selected<br>- Previews show for each image<br>- Can remove individual images<br>- First image marked as main | Logged in as Vendor |

---

### Product Management (/vendor/products or Registration Management)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| PREG04 | View registered products | 1. Login as Vendor<br>2. Go to product registration management | - Product list displays<br>- Shows: name, status (Pending/Approved/Rejected)<br>- Filter by status available<br>- Can view details | Logged in as Vendor |
| PREG05 | View rejected product reason | 1. Go to product management<br>2. Find a rejected product<br>3. Click to view details | - Rejection reason displayed<br>- Can edit and resubmit<br>- Original data shown | Has rejected product |
