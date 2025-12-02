# Feature 8: Farm Profile Management - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_Farm |
| **Feature** | Farm Profile Management |
| **Module** | Farm Profiles, Crops, Weather Integration |
| **Total Test Cases** | 14 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 8.1 Farm List View

| TC ID | TC_FARM_001 |
|-------|------------|
| **Description** | Verify farm list page displays correctly |
| **Pre-conditions** | User logged in as Vendor/Farmer |
| **Procedure** | 1. Navigate to "My Farms" section<br>2. Observe the farm list page |
| **Expected Results** | - Page shows list/grid of farm profiles<br>- Each card shows: Farm Name, Location, Size, Status<br>- "Add New Farm" button visible<br>- Search/filter options available |

| TC ID | TC_FARM_002 |
|-------|------------|
| **Description** | Verify empty state when no farms exist |
| **Pre-conditions** | User has no farm profiles |
| **Procedure** | 1. Navigate to "My Farms"<br>2. Observe empty state |
| **Expected Results** | - Empty state illustration/message displayed<br>- "You haven't added any farms yet"<br>- Prominent "Create Your First Farm" button<br>- Helpful tips or guide link |

### 8.2 Create Farm Profile

| TC ID | TC_FARM_003 |
|-------|------------|
| **Description** | Verify create farm form layout |
| **Pre-conditions** | User on farm list page |
| **Procedure** | 1. Click "Add New Farm" button<br>2. Observe the form |
| **Expected Results** | - Form displays with sections: Basic Info, Location, Details<br>- Fields: Farm Name, Address, Size (hectares), Description<br>- Image upload area for farm photos<br>- Soil type selection (optional)<br>- Save and Cancel buttons |

| TC ID | TC_FARM_004 |
|-------|------------|
| **Description** | Verify create farm with valid data |
| **Pre-conditions** | User on create farm form |
| **Procedure** | 1. Enter Farm Name: "Sunny Valley Farm"<br>2. Enter Address: "123 Rural Road, District A"<br>3. Enter Size: 5.5 hectares<br>4. Add description<br>5. Upload farm image<br>6. Click "Create Farm" |
| **Expected Results** | - Form validates successfully<br>- Loading indicator during save<br>- Success: "Farm profile created!"<br>- Redirected to farm detail or list<br>- New farm appears in list |

| TC ID | TC_FARM_005 |
|-------|------------|
| **Description** | Verify create farm - validation errors |
| **Pre-conditions** | User on create farm form |
| **Procedure** | 1. Leave Farm Name empty<br>2. Leave Address empty<br>3. Enter Size: -10 (invalid)<br>4. Click "Create Farm" |
| **Expected Results** | - Inline validation errors shown<br>- "Farm name is required"<br>- "Address is required"<br>- "Size must be a positive number"<br>- Form does not submit |

### 8.3 Farm Detail View

| TC ID | TC_FARM_006 |
|-------|------------|
| **Description** | Verify farm detail page layout |
| **Pre-conditions** | User has at least one farm |
| **Procedure** | 1. Click on a farm card from list<br>2. Observe farm detail page |
| **Expected Results** | - Header shows farm name and status<br>- Photo gallery or main image<br>- Location with map (if integrated)<br>- Farm statistics: Size, Crops count<br>- Tabs: Overview, Crops, Weather, Settings |

| TC ID | TC_FARM_007 |
|-------|------------|
| **Description** | Verify edit farm profile |
| **Pre-conditions** | User on farm detail page |
| **Procedure** | 1. Click "Edit" button<br>2. Modify farm name to "Updated Farm Name"<br>3. Update size to 6.0 hectares<br>4. Click "Save Changes" |
| **Expected Results** | - Edit mode activates or modal opens<br>- Current data pre-filled<br>- Changes can be made<br>- Success: "Farm updated successfully"<br>- Detail page reflects changes |

### 8.4 Crop Management

| TC ID | TC_FARM_008 |
|-------|------------|
| **Description** | Verify crops list within farm |
| **Pre-conditions** | User on farm detail page |
| **Procedure** | 1. Click on "Crops" tab<br>2. Observe crops list |
| **Expected Results** | - List shows crops planted on this farm<br>- Each entry: Crop Name, Area, Plant Date, Expected Harvest<br>- "Add Crop" button visible<br>- Status indicators (Growing, Harvested) |

| TC ID | TC_FARM_009 |
|-------|------------|
| **Description** | Verify add crop to farm |
| **Pre-conditions** | User on farm crops tab |
| **Procedure** | 1. Click "Add Crop" button<br>2. Select crop type: "Rice"<br>3. Enter planting area: 2 hectares<br>4. Enter planting date<br>5. Click "Add" |
| **Expected Results** | - Add crop modal/form opens<br>- Crop type dropdown with options<br>- Validation on area (≤ farm size)<br>- Success: "Crop added to farm"<br>- Crop appears in list |

| TC ID | TC_FARM_010 |
|-------|------------|
| **Description** | Verify crop area validation |
| **Pre-conditions** | Farm size is 5 hectares |
| **Procedure** | 1. Open add crop form<br>2. Enter area: 10 hectares (exceeds farm)<br>3. Try to submit |
| **Expected Results** | - Validation error: "Area exceeds available farm space"<br>- Shows available space remaining<br>- Form does not submit |

### 8.5 Weather Integration

| TC ID | TC_FARM_011 |
|-------|------------|
| **Description** | Verify weather widget on farm page |
| **Pre-conditions** | Farm has valid location/address |
| **Procedure** | 1. Navigate to farm detail page<br>2. Locate weather widget/section |
| **Expected Results** | - Weather widget displays current weather<br>- Shows: Temperature, Humidity, Conditions<br>- Weather icon matches conditions<br>- Location shown (farm address)<br>- Last updated timestamp |

| TC ID | TC_FARM_012 |
|-------|------------|
| **Description** | Verify weather forecast display |
| **Pre-conditions** | User on farm page with weather widget |
| **Procedure** | 1. Click "View Forecast" or expand weather section<br>2. Observe forecast display |
| **Expected Results** | - Shows 5-7 day forecast<br>- Each day: Date, High/Low temp, Icon, Conditions<br>- Precipitation probability shown<br>- Scroll/swipe through days |

| TC ID | TC_FARM_013 |
|-------|------------|
| **Description** | Verify weather data refresh |
| **Pre-conditions** | Weather widget visible |
| **Procedure** | 1. Click refresh icon on weather widget<br>2. Observe refresh behavior |
| **Expected Results** | - Loading spinner appears<br>- Data updates (timestamp changes)<br>- Success feedback or animation<br>- Error message if API fails |

### 8.6 Delete Farm

| TC ID | TC_FARM_014 |
|-------|------------|
| **Description** | Verify delete farm functionality |
| **Pre-conditions** | User has a farm profile |
| **Procedure** | 1. Go to farm settings or detail page<br>2. Click "Delete Farm" button<br>3. Read confirmation dialog<br>4. Type farm name to confirm<br>5. Click "Delete" |
| **Expected Results** | - Confirmation dialog with warning<br>- "This action cannot be undone"<br>- Requires typing farm name to confirm<br>- After delete: Redirected to farm list<br>- Farm no longer in list |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 14 |
| Priority - High | 6 |
| Priority - Medium | 5 |
| Priority - Low | 3 |
