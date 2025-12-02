# Feature_Inventory - Inventory Management UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Inventory |
| **Test requirement** | Staff/Admin Inventory panel available |
| **Number of TCs** | 5 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 5 | 0 |
| Round 2 | 0 | 0 | 5 | 0 |
| Round 3 | 0 | 0 | 5 | 0 |

---

## Test Cases

### Inventory Management Panel (Staff/Admin)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| INV01 | View inventory list | 1. Login as Staff/Admin<br>2. Navigate to Inventory Management panel | - Inventory table displays<br>- Columns: Product, SKU, Batch, Quantity, Expiry<br>- Pagination works<br>- Loading spinner on fetch | Logged in as Staff/Admin |
| INV02 | Search inventory by product | 1. Go to Inventory panel<br>2. Enter product name in search box<br>3. Click search or press Enter | - Results filtered<br>- Matching products shown<br>- "Không tìm thấy" if no match | Logged in as Staff/Admin |
| INV03 | Add new batch inventory | 1. Go to Inventory panel<br>2. Click "Thêm lô hàng" button<br>3. Fill form: select product, quantity, expiry date<br>4. Click "Lưu" | - Add batch modal opens<br>- Form validation works<br>- Success toast on save<br>- New batch in list | Logged in as Staff/Admin |
| INV04 | Export inventory report | 1. Go to Inventory panel<br>2. Click "Xuất báo cáo" button<br>3. Select export format (Excel/PDF) | - Export dialog shows<br>- Download starts<br>- File downloads to device | Logged in as Staff/Admin |
| INV05 | View low stock alerts | 1. Go to Inventory panel<br>2. Check "Sắp hết hàng" filter or alerts section | - Products with low stock highlighted<br>- Warning icon shows<br>- Quantity shown in red if below threshold | Logged in as Staff/Admin |
