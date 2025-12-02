# Feature_Inventory - Inventory Management UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Inventory Management |
| **Test requirement** | Admin/Staff Inventory Panel available |
| **Number of TCs** | 14 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 14 | 0 |
| Round 2 | 0 | 0 | 14 | 0 |
| Round 3 | 0 | 0 | 14 | 0 |

---

## Test Cases

### Batch Inventory List

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| INV01 | View batch inventory page | 1. Login as Admin/Staff<br>2. Navigate to Inventory Management<br>3. Click "Batch Inventory" | - Batch table displays<br>- Columns: ID, Product, Quantity, Import Date, Expiry, Status<br>- Pagination visible<br>- Search and filter available | Logged in as Admin/Staff |
| INV02 | Search batch inventory | 1. On batch inventory page<br>2. Type product name in search<br>3. Press Enter | - Results filter by search term<br>- Matching batches shown<br>- "Không tìm thấy" if no match | Batch data exists |
| INV03 | Filter by status | 1. On batch inventory page<br>2. Click Status dropdown<br>3. Select "Hết hạn" (Expired) | - Table shows expired batches only<br>- Status badge shows filtered<br>- Clear filter available | Batch data exists |

---

### Create New Batch

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| INV04 | Open create batch form | 1. On batch inventory page<br>2. Click "Thêm mới" button | - Modal/form opens<br>- Fields: Product, Quantity, Import Date, Expiry<br>- Required fields marked (*) | Admin/Staff logged in |
| INV05 | Create batch - valid data | 1. Open create batch form<br>2. Select Product from dropdown<br>3. Enter Quantity: 100<br>4. Select Import Date: today<br>5. Select Expiry: +6 months<br>6. Click "Lưu" | - Loading shows<br>- Success toast "Tạo lô hàng thành công"<br>- Modal closes<br>- New batch in table | Form open |
| INV06 | Create batch - empty fields | 1. Open create batch form<br>2. Leave all fields empty<br>3. Click "Lưu" | - Validation errors show<br>- "Sản phẩm là bắt buộc"<br>- "Số lượng là bắt buộc"<br>- Form not submitted | Form open |
| INV07 | Create batch - negative quantity | 1. Open create batch form<br>2. Select product<br>3. Enter Quantity: -50<br>4. Click "Lưu" | - Validation error "Số lượng phải lớn hơn 0"<br>- Form not submitted | Form open |

---

### Edit & Export Batch

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| INV08 | Edit batch quantity | 1. On batch list<br>2. Click edit icon on a batch<br>3. Change quantity: 100 → 150<br>4. Click "Cập nhật" | - Edit form opens with data<br>- Success toast "Cập nhật thành công"<br>- Table shows new quantity | Batch exists |
| INV09 | View export inventory page | 1. Navigate to "Export Inventory"<br>2. Observe page | - Export history table<br>- Columns: ID, Product, Qty, Date, Destination<br>- "Xuất kho" button visible | Admin/Staff logged in |
| INV10 | Create export record | 1. On export inventory<br>2. Click "Xuất kho"<br>3. Select batch, enter qty: 50<br>4. Enter destination<br>5. Click "Xác nhận" | - Export recorded<br>- Success toast<br>- Batch quantity reduced<br>- Export in history | Available batch exists |
| INV11 | Export exceeds available | 1. Open export form<br>2. Select batch with 100 units<br>3. Enter qty: 150<br>4. Click "Xác nhận" | - Error "Số lượng xuất vượt quá tồn kho (100)"<br>- Form not submitted | Batch with limited stock |

---

### Inventory Alerts

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| INV12 | View low stock warning | 1. Navigate to inventory dashboard<br>2. Check low stock section | - Low stock items highlighted<br>- Warning badge with count<br>- Red/orange indicator | Products with low stock |
| INV13 | Filter expiring soon | 1. On batch inventory<br>2. Click "Sắp hết hạn" filter | - Shows batches expiring in 30 days<br>- Expiry date in warning color<br>- Days remaining shown | Batches near expiry |
| INV14 | Pagination in batch list | 1. On batch inventory (>10 records)<br>2. Click page 2<br>3. Change items per page to 25 | - Page 2 data loads<br>- Items per page updates<br>- Current page indicator | >10 batch records |
