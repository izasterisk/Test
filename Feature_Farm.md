# Feature_Farm - Farm Profile UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Farm Profile Management |
| **Test requirement** | Farm Profiles, Crops, Weather pages available |
| **Number of TCs** | 14 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 14 | 0 |
| Round 2 | 0 | 0 | 14 | 0 |
| Round 3 | 0 | 0 | 14 | 0 |

---

## Test Cases

### Farm List View

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM01 | View farm list page | 1. Login as Vendor/Farmer<br>2. Navigate to "Nông trại của tôi" | - Farm list/grid displays<br>- Each card: Name, Location, Size, Status<br>- "Thêm nông trại" button visible<br>- Search/filter available | Logged in |
| FARM02 | View empty farm state | 1. Login (no farms created)<br>2. Navigate to farm list | - Empty state illustration<br>- "Bạn chưa có nông trại nào"<br>- "Tạo nông trại đầu tiên" button<br>- Helpful tips shown | No farms exist |

---

### Create Farm Profile

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM03 | View create farm form | 1. On farm list<br>2. Click "Thêm nông trại" | - Form displays with sections<br>- Fields: Name, Address, Size (ha), Description<br>- Image upload area<br>- Save and Cancel buttons | Logged in |
| FARM04 | Create farm - valid data | 1. Open create farm form<br>2. Enter Name: "Nông trại Sunny"<br>3. Enter Address: "123 Đường ABC"<br>4. Enter Size: 5.5 ha<br>5. Add description<br>6. Upload image<br>7. Click "Tạo nông trại" | - Loading indicator<br>- Success "Tạo nông trại thành công!"<br>- Redirect to farm detail/list<br>- New farm in list | Form open |
| FARM05 | Create farm - validation errors | 1. Open create form<br>2. Leave Name empty<br>3. Leave Address empty<br>4. Enter Size: -10<br>5. Click submit | - Inline errors shown<br>- "Tên nông trại là bắt buộc"<br>- "Địa chỉ là bắt buộc"<br>- "Diện tích phải > 0" | Form open |

---

### Farm Detail View

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM06 | View farm detail page | 1. On farm list<br>2. Click a farm card | - Farm name and status header<br>- Photo gallery/main image<br>- Location info<br>- Farm statistics<br>- Tabs: Overview, Crops, Weather | Farm exists |
| FARM07 | Edit farm profile | 1. On farm detail<br>2. Click "Chỉnh sửa"<br>3. Update name to "Updated Farm"<br>4. Update size to 6.0 ha<br>5. Click "Lưu" | - Edit mode activates<br>- Current data pre-filled<br>- Success "Cập nhật thành công"<br>- Detail page reflects changes | Farm detail open |

---

### Crop Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM08 | View crops tab | 1. On farm detail<br>2. Click "Cây trồng" tab | - Crops list for this farm<br>- Each entry: Name, Area, Plant Date, Harvest Date<br>- "Thêm cây trồng" button<br>- Status indicators | Farm detail open |
| FARM09 | Add crop to farm | 1. On crops tab<br>2. Click "Thêm cây trồng"<br>3. Select crop: "Lúa"<br>4. Enter area: 2 ha<br>5. Enter planting date<br>6. Click "Thêm" | - Add crop form opens<br>- Crop type dropdown available<br>- Validation on area<br>- Success "Đã thêm cây trồng"<br>- Crop in list | Crops tab open |
| FARM10 | Add crop - area exceeds farm | 1. Farm size: 5 ha<br>2. Open add crop form<br>3. Enter area: 10 ha<br>4. Try submit | - Error "Diện tích vượt quá diện tích nông trại"<br>- Available space shown<br>- Form not submitted | Farm size limited |

---

### Weather Integration

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM11 | View weather widget | 1. On farm detail<br>2. Locate weather section | - Current weather displays<br>- Temperature, Humidity, Conditions<br>- Weather icon matches<br>- Farm location shown<br>- Last updated timestamp | Farm has valid address |
| FARM12 | View weather forecast | 1. On farm detail<br>2. Click "Xem dự báo" or expand | - 5-7 day forecast shows<br>- Each day: Date, High/Low, Icon<br>- Precipitation probability<br>- Scroll/swipe through days | Weather widget visible |
| FARM13 | Refresh weather data | 1. Weather widget visible<br>2. Click refresh icon | - Loading spinner<br>- Data updates<br>- Timestamp refreshes<br>- Error if API fails | Weather widget visible |

---

### Delete Farm

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FARM14 | Delete farm | 1. On farm detail/settings<br>2. Click "Xóa nông trại"<br>3. Type farm name to confirm<br>4. Click "Xóa" | - Confirmation dialog with warning<br>- "Không thể hoàn tác"<br>- Requires typing name<br>- After delete: Redirect to list<br>- Farm removed | Farm exists |
