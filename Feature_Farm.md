# Feature_Farm - Farm & Crop UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Farm & Crop |
| **Test requirement** | Create Farm, Farm List, Farm Detail pages available |
| **Number of TCs** | 5 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 5 | 0 |
| Round 2 | 0 | 0 | 5 | 0 |
| Round 3 | 0 | 0 | 5 | 0 |

---

## Test Cases

### Create Farm Page (/create-farm)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM01 | Create new farm | 1. Login as customer/farmer<br>2. Navigate to /create-farm<br>3. Fill farm details:<br>- Farm name<br>- Location (map picker)<br>- Area size<br>- Description<br>4. Click "Tạo nông trại" | - Form validates all fields<br>- Map location picker works<br>- Loading spinner on submit<br>- Success toast "Tạo nông trại thành công"<br>- Redirect to farm detail | Logged in |
| FARM02 | Create farm with invalid data | 1. Go to /create-farm<br>2. Leave farm name empty<br>3. Click "Tạo nông trại" | - Validation error shows<br>- Required fields highlighted<br>- Form not submitted | Logged in |

---

### Farm List Page (/farms)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM03 | View farm list | 1. Login<br>2. Navigate to farm list page | - Loading spinner first<br>- Farm cards displayed<br>- Each card shows: name, location, area<br>- "Tạo nông trại" button visible | Logged in |

---

### Farm Detail Page (/farm/:id)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM04 | View farm detail | 1. Go to farm list<br>2. Click on a farm card | - Farm detail page loads<br>- Farm info displayed<br>- Weather widget shows<br>- Crop list section visible<br>- CO2 info (if available) | Farm exists |
| FARM05 | View weather for farm | 1. On farm detail page<br>2. Check weather section | - Current weather displays<br>- Temperature, humidity, conditions<br>- Hourly forecast (if available)<br>- Weather icon shows | Farm has location |
