# Feature_Inventory - Inventory Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Inventory |
| **Test requirement** | API and design are available |
| **Number of TCs** | 15 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 15 | 0 |
| Round 2 | 0 | 0 | 15 | 0 |
| Round 3 | 0 | 0 | 15 | 0 |

---

## Test Cases

### Batch Inventory (Import)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| INV01 | Create batch inventory | 1. Call POST `/api/BatchInventory`<br>2. Send product ID, quantity, batch number | - Batch created<br>- Stock increased<br>- Status 200 OK | Product exists |
| INV02 | Get all batch inventories | 1. Call GET `/api/BatchInventory?page=1&pageSize=20` | - List of batches returned<br>- Pagination info | Batches exist |
| INV03 | Get batch by product ID | 1. Call GET `/api/BatchInventory/product/{productId}` | - Only batches for product returned | Product has batches |
| INV04 | Get batch by vendor ID | 1. Call GET `/api/BatchInventory/vendor/{vendorId}` | - Only vendor's batches returned | Vendor has batches |
| INV05 | Update batch inventory | 1. Call PUT `/api/BatchInventory/{id}`<br>2. Send updated quantity/info | - Batch updated<br>- Status 200 OK | Batch exists |
| INV06 | Quality check batch | 1. Call POST `/api/BatchInventory/{id}/quality-check`<br>2. Send inspector ID, status, notes | - Quality check recorded<br>- Status 200 OK | Batch exists |
| INV07 | Get serials by batch ID | 1. Call GET `/api/BatchInventory/{batchId}/serials` | - List of serial numbers returned | Batch with serials exists |

---

### Export Inventory

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| INV08 | Create export inventory (Damage) | 1. Login as Admin/Staff<br>2. Call POST `/api/ExportInventory`<br>3. Send MovementType = Damage | - Export record created<br>- Stock decreased<br>- Status 201 Created | Stock available |
| INV09 | Create export with type Sale (not allowed) | 1. Login as Admin/Staff<br>2. Call POST `/api/ExportInventory`<br>3. Send MovementType = Sale | - Error: Sale type not allowed<br>- Status 400 Bad Request | None |
| INV10 | Get all export inventories | 1. Login as Admin/Staff<br>2. Call GET `/api/ExportInventory?page=1` | - List of exports returned | Logged in as Admin/Staff |
| INV11 | Get exports filtered by type | 1. Call GET `/api/ExportInventory?movementType=Damage` | - Only Damage exports returned | Exports exist |
| INV12 | Get identity numbers by product | 1. Login<br>2. Call GET `/api/ExportInventory/identity-numbers/{productId}` | - List of batch/serial numbers available | Product has stock |

---

### Product Serial

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| INV13 | View available serials | 1. Login<br>2. Get identity numbers for serialized product | - List of available serial numbers | Product requires serial |
| INV14 | Export with serial number | 1. Login as Admin/Staff<br>2. Ship order with serial number | - Serial marked as sold<br>- Cannot reuse | Serial available |
| INV15 | Export with duplicate serial (not allowed) | 1. Try to export already-used serial | - Error: Serial already used<br>- Status 400 Bad Request | Serial already exported |
