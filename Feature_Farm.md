# Feature_Farm - Farm & Crop Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Farm & Crop |
| **Test requirement** | API and design are available |
| **Number of TCs** | 12 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 12 | 0 |
| Round 2 | 0 | 0 | 12 | 0 |
| Round 3 | 0 | 0 | 12 | 0 |

---

## Test Cases

### Farm Profile

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM01 | Create farm profile | 1. Login<br>2. Call POST `/api/FarmProfile`<br>3. Send farm name, area, location | - Farm profile created<br>- Owner ID from token<br>- Status 201 Created | Logged in |
| FARM02 | Get farm by ID | 1. Login<br>2. Call GET `/api/FarmProfile/{id}` | - Farm details returned<br>- Includes crops, address | Farm exists |
| FARM03 | Get farms by user ID | 1. Login<br>2. Call GET `/api/FarmProfile/User/{userId}` | - List of user's farms | User has farms |
| FARM04 | Update farm profile | 1. Login<br>2. Call PATCH `/api/FarmProfile/{id}`<br>3. Update farm name/area | - Farm updated<br>- Status 200 OK | Farm exists |
| FARM05 | Get farm with non-existent ID | 1. Login<br>2. Call GET `/api/FarmProfile/99999` | - Error: Farm not found<br>- Status 404 Not Found | None |

---

### Crop Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM06 | Add crops to farm | 1. Login<br>2. Call POST `/api/farm/{farmId}/Crop`<br>3. Send list of crops | - Crops added to farm<br>- Status 201 Created | Farm exists |
| FARM07 | Add duplicate crop (not allowed) | 1. Login<br>2. Try to add crop with same name + plant date | - Error: Duplicate crop<br>- Status 400 Bad Request | Crop exists |
| FARM08 | Update crops | 1. Login<br>2. Call PATCH `/api/farm/{farmId}/Crop`<br>3. Update crop status/info | - Crops updated<br>- Status 200 OK | Farm has crops |
| FARM09 | Add crop with invalid plant method | 1. Login<br>2. Add crop with incompatible plant method | - Error: Invalid plant method for crop type<br>- Status 400 Bad Request | Farm exists |

---

### CO2 & Weather

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM10 | Create CO2 footprint data | 1. Login<br>2. Call POST `/api/CO2`<br>3. Send farm ID, emission data | - CO2 data recorded<br>- Status 201 Created | Farm exists |
| FARM11 | Get weather by farm ID | 1. Login<br>2. Call GET `/api/Weather/farm/{farmId}` | - Current weather returned<br>- Based on farm location | Farm with address |
| FARM12 | Get hourly weather forecast | 1. Login<br>2. Call GET `/api/Weather/farm/{farmId}/hourly` | - Hourly forecast returned | Farm with address |
