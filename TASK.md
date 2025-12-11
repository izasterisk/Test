# Recipe Sharing Platform - Phân Công Dự Án

## 📋 Tổng Quan Dự Án

**Công nghệ sử dụng:**
- ASP.NET Core 8 Razor Pages
- Entity Framework Core 8
- SQL Server
- ASP.NET Core Identity
- SignalR (chỉ cho Comments & Likes real-time)
- Cloudinary (lưu trữ hình ảnh)
- Bootstrap 5 + jQuery/Vanilla JavaScript

**Thời gian:** 5-7 ngày

**Số thành viên:** 5 người

---

## 👥 Phân Công Chi Tiết

### 👤 **Thành Viên 1: Setup Project + Authentication & User Management**

**Thời gian:** 2-3 ngày

#### **Giai Đoạn 1: Setup Project (Ngày 1 - ƯU TIÊN CAO NHẤT)**

**Nhiệm vụ Setup:**
1. Tạo ASP.NET Core 8 Razor Pages project
2. Cài đặt các NuGet packages cần thiết:
   - Entity Framework Core + SQL Server
   - ASP.NET Core Identity
   - CloudinaryDotNet
   - SignalR
3. Cấu hình `appsettings.json` với connection string và Cloudinary credentials
4. Tạo tất cả Entity Models (15 bảng theo database schema)
5. Tạo `ApplicationDbContext.cs` với tất cả DbSet và relationships
6. Cấu hình `Program.cs` (DbContext, Identity, SignalR, Services DI)
7. Chạy migrations để tạo database
8. Tạo `ICloudinaryService` / `CloudinaryService` để upload ảnh (service dùng chung cho cả team)
9. Tạo `_Layout.cshtml` với Bootstrap 5

**Bàn giao cho team:**
- ✅ Project chạy được
- ✅ Database đã tạo với đầy đủ 15 bảng
- ✅ Tất cả Models đã có
- ✅ CloudinaryService sẵn sàng sử dụng
- ✅ Layout master page

#### **Giai Đoạn 2: Module Authentication & User (Ngày 2-3)**

**Backend Services cần làm:**
- `IUserService` / `UserService` với các method:
  - Đăng ký user mới
  - Đăng nhập / Đăng xuất
  - Lấy thông tin user
  - Cập nhật profile
  - Follow/Unfollow user
  - Lấy danh sách followers/following

**Razor Pages cần tạo:**

1. **Login Page** - Form đăng nhập với email và password
2. **Register Page** - Form đăng ký với username, email, password, họ tên, bio
3. **Logout** - Xử lý đăng xuất
4. **Profile Page** - Hiển thị thông tin user với các tabs:
   - Công Thức Của Tôi
   - Đã Lưu
   - Người Theo Dõi
   - Đang Theo Dõi
   - Nút Follow/Unfollow (nếu xem profile người khác)
5. **Edit Profile Page** - Form chỉnh sửa thông tin cá nhân và upload avatar

**UI Components:**
- Navbar với Login/Register buttons hoặc Profile dropdown
- Profile card hiển thị avatar, tên, bio
- Nút Follow/Unfollow với số lượng followers

**Bảng Database phụ trách:** `Users`, `Followers`

---

### 👤 **Thành Viên 2: Recipe Management (CRUD)**

**Thời gian:** 3-4 ngày

**Backend Services cần làm:**
- `IRecipeService` / `RecipeService` với các method:
  - Lấy danh sách recipes (có tìm kiếm, lọc, phân trang)
  - Lấy chi tiết recipe
  - Tạo recipe mới
  - Cập nhật recipe
  - Xóa recipe
  - Tăng view count
- `ICategoryService` / `CategoryService`:
  - Lấy danh sách categories

**Razor Pages cần tạo:**

1. **Index/Browse Page** - Trang chủ hiển thị danh sách công thức:
   - Grid hoặc list view
   - Thanh tìm kiếm
   - Filter theo category
   - Phân trang
   - Sắp xếp (mới nhất, phổ biến, nhiều likes)
   - Recipe card hiển thị: ảnh, tên món, tác giả, thời gian, số likes

2. **Recipe Details Page** - Chi tiết công thức:
   - Header: tên món, tác giả, category
   - Gallery nhiều ảnh với slider
   - Thông tin: thời gian chuẩn bị, nấu, số người ăn, độ khó
   - Mô tả
   - Danh sách nguyên liệu (sẽ có calculator từ Thành viên 4)
   - Các bước thực hiện với ảnh
   - Số lượt xem
   - Khu vực cho Like button (Thành viên 3)
   - Khu vực cho Comments (Thành viên 3)
   - Nút Edit/Delete (nếu là chủ sở hữu)

3. **Create Recipe Page** - Form tạo công thức mới:
   - Thông tin cơ bản: tên, mô tả, category, thời gian, servings, độ khó
   - Upload nhiều ảnh (dùng Cloudinary) với preview
   - Sắp xếp thứ tự ảnh
   - Thêm/xóa nguyên liệu động (JavaScript)
   - Thêm/xóa các bước động (JavaScript)
   - Có thể upload ảnh cho từng bước

4. **Edit Recipe Page** - Form chỉnh sửa (giống Create nhưng đã có data)

5. **Delete Confirmation Page** - Xác nhận xóa công thức

**UI Components:**
- Recipe card component
- Image upload với preview
- Form rows có thể thêm/xóa động
- Image gallery/slider

**JavaScript cần viết:**
- Logic thêm/xóa dòng nguyên liệu và bước
- Preview ảnh khi upload
- Sắp xếp lại ảnh (drag & drop hoặc nút lên/xuống)
- Validation form

**Bảng Database phụ trách:** `Recipes`, `Categories`, `RecipeImages`, `RecipeIngredients`, `RecipeSteps`

---

### 👤 **Thành Viên 3: Social Features + SignalR Real-time**

**Thời gian:** 3 ngày

**SignalR Hub cần tạo:**
- `CommentHub.cs` để xử lý real-time cho:
  - Comments mới
  - Replies
  - Likes
  - Join/Leave recipe group

**Backend Services cần làm:**
- `ICommentService` / `CommentService`:
  - Lấy comments của recipe
  - Thêm comment mới (có thể có rating 1-5 sao)
  - Thêm reply cho comment
  - Sửa/xóa comment
- `ILikeService` / `LikeService`:
  - Toggle like recipe (trả về số lượng likes mới)
  - Toggle like comment
  - Kiểm tra user đã like chưa
- `ISavedRecipeService` / `SavedRecipeService`:
  - Lưu/bỏ lưu recipe
  - Lấy danh sách recipes đã lưu

**Razor Pages cần tạo:**

1. **Saved Recipes Page** - Hiển thị danh sách công thức đã lưu của user

**Partial Views cần tạo:**

2. **_CommentSection.cshtml** - Component phần comments:
   - Form nhập comment với rating sao
   - Danh sách comments hiển thị:
     - Avatar, username, thời gian
     - Nội dung comment và rating
     - Nút like comment với số lượng
     - Nút reply
     - Nút edit/delete (nếu là chủ)
   - Replies lồng nhau (thụt lề)
   - Cập nhật real-time khi có comment mới

3. **_LikeButton.cshtml** - Component nút like:
   - Icon trái tim
   - Số lượng likes
   - Toggle liked/unliked
   - Animation khi click
   - Cập nhật real-time

**UI Components:**
- Comment card
- Reply form
- Star rating (có thể click)
- Like button với animation
- Save/Bookmark button

**JavaScript cần viết:**
- SignalR client connection
- Xử lý nhận comment mới real-time
- Xử lý nhận like real-time
- Gửi comment/like qua SignalR
- Animation và update DOM

**Bảng Database phụ trách:** `RecipeLikes`, `SavedRecipes`, `Comments`, `CommentLikes`

---

### 👤 **Thành Viên 4: Ingredient Calculator & Shopping List**

**Thời gian:** 3 ngày

**Backend Services cần làm:**
- `IShoppingListService` / `ShoppingListService`:
  - Tạo/lấy shopping list của user
  - Thêm recipe vào list (tự động tính nguyên liệu theo servings)
  - Thêm item thủ công
  - Cập nhật trạng thái check/uncheck item
  - Xóa item
  - Xóa tất cả items đã hoàn thành
  - Merge nguyên liệu trùng lặp
  - Nhóm items theo category

**Razor Pages cần tạo:**

1. **Shopping List Page** - Trang danh sách mua sắm:
   - Nút "Tạo từ Kế Hoạch Tuần"
   - Nút "Thêm Thủ Công"
   - Hiển thị items được nhóm theo category (Rau củ, Thịt, Gia vị...)
   - Mỗi item có checkbox (check/uncheck qua AJAX)
   - Nút xóa item
   - Nút "Xóa Đã Hoàn Thành"

2. **Add Recipe to List** - Modal hoặc trang riêng:
   - Tìm kiếm recipe
   - Chọn recipe
   - Điều chỉnh servings
   - Preview nguyên liệu sẽ thêm
   - Xác nhận thêm

**Partial View cần tạo:**

3. **_IngredientCalculator.cshtml** - Component tính toán nguyên liệu:
   - Nhúng vào Recipe Details page
   - Bộ chọn số người ăn (buttons: 2, 4, 6, 8 hoặc input tùy chỉnh)
   - Danh sách nguyên liệu tự động tính lại số lượng
   - Nút "Thêm vào Shopping List"

**UI Components:**
- Servings selector
- Shopping list item với checkbox
- Category group header
- Form thêm item thủ công

**JavaScript cần viết:**
- Logic tính toán nguyên liệu khi thay đổi servings
- AJAX toggle checkbox item
- AJAX xóa item
- Update DOM khi thay đổi

**Bảng Database phụ trách:** `ShoppingLists`, `ShoppingListItems`

---

### 👤 **Thành Viên 5: Meal Planning**

**Thời gian:** 3 ngày

**Backend Services cần làm:**
- `IMealPlanService` / `MealPlanService`:
  - Lấy kế hoạch bữa ăn theo tuần
  - Thêm recipe vào ngày và bữa cụ thể
  - Xóa recipe khỏi meal plan
  - Cập nhật ghi chú
  - Tạo shopping list từ tất cả recipes trong tuần

**Razor Pages cần tạo:**

1. **Meal Plan Calendar Page** - Trang lịch tuần:
   - Lưới 7 ngày x 4 bữa (Sáng, Trưa, Tối, Snack)
   - Navigation: Tuần Trước / Tuần Sau
   - Mỗi ô bữa ăn:
     - Hiển thị nút [+] nếu chưa có món
     - Hiển thị recipe card nếu đã thêm (ảnh, tên, servings)
     - Nút X để xóa
   - Nút "Tạo Shopping List Cho Tuần Này" ở cuối trang

2. **Add Meal Modal** - Modal thêm món vào bữa ăn:
   - Hiển thị ngày và bữa đã chọn
   - Tìm kiếm recipe
   - Điều chỉnh servings
   - Preview thông tin recipe
   - Nút xác nhận thêm

3. **Generate Shopping List Page** - Trang tạo shopping list:
   - Tổng hợp tất cả recipes trong tuần
   - Hiển thị preview nguyên liệu đã merge
   - Nút xác nhận → Thêm vào Shopping List
   - Redirect đến Shopping List page

**UI Components:**
- Calendar grid (responsive)
- Meal slot (ô bữa ăn)
- Recipe card trong meal
- Modal thêm recipe
- Week navigation

**JavaScript cần viết:**
- Mở/đóng modal thêm meal
- AJAX thêm recipe vào meal
- AJAX xóa recipe khỏi meal
- Navigation giữa các tuần
- Search recipes trong modal

**Bảng Database phụ trách:** `MealPlans`, `MealPlanRecipes`

---

## 🔗 Tích Hợp Giữa Các Module

### **Luồng phụ thuộc:**
1. **Thành viên 1** setup xong → Các thành viên khác bắt đầu làm
2. **Thành viên 2, 3, 4, 5** làm song song
3. **Tích hợp:**
   - Thành viên 3 nhúng Comments/Likes vào Recipe Details (của Thành viên 2)
   - Thành viên 4 nhúng Calculator vào Recipe Details (của Thành viên 2)
   - Thành viên 5 dùng Recipe search (của Thành viên 2) và Shopping List service (của Thành viên 4)

### **Điểm tích hợp quan trọng:**

**Recipe Details Page (Thành viên 2):**
- Nhúng `_IngredientCalculator` partial view (Thành viên 4)
- Nhúng `_LikeButton` partial view (Thành viên 3)
- Nhúng `_CommentSection` partial view (Thành viên 3)

**Meal Plan (Thành viên 5):**
- Sử dụng Recipe search component (Thành viên 2)
- Gọi `IShoppingListService.AddRecipeToListAsync()` (Thành viên 4)

**Shopping List (Thành viên 4):**
- Nhận data từ Meal Plan (Thành viên 5)
- Sử dụng Ingredient Calculator logic

---

## ✅ Checklist Kiểm Tra

### **Thành viên 1 - Authentication:**
- [ ] User đăng ký được với dữ liệu hợp lệ
- [ ] User đăng nhập được
- [ ] User xem được profile của mình và người khác
- [ ] User chỉnh sửa được profile và upload avatar lên Cloudinary
- [ ] User follow/unfollow được người khác
- [ ] Số followers cập nhật đúng

### **Thành viên 2 - Recipes:**
- [ ] Hiển thị danh sách recipes với phân trang
- [ ] Tìm kiếm và lọc recipes hoạt động
- [ ] Xem chi tiết recipe đầy đủ thông tin
- [ ] Tạo recipe với nhiều ảnh upload lên Cloudinary
- [ ] Thêm/xóa nguyên liệu và bước động
- [ ] Chỉnh sửa và xóa recipe của mình
- [ ] View count tăng khi xem recipe

### **Thành viên 3 - Social + SignalR:**
- [ ] Like/unlike recipe và số likes cập nhật real-time
- [ ] Comment hiển thị ngay lập tức cho tất cả users (SignalR)
- [ ] Reply comments hoạt động
- [ ] Sửa/xóa comment của mình
- [ ] Đánh giá sao khi comment
- [ ] Lưu/bỏ lưu recipe
- [ ] Xem danh sách recipes đã lưu

### **Thành viên 4 - Shopping List:**
- [ ] Ingredient calculator tính đúng số lượng khi đổi servings
- [ ] Thêm recipe vào shopping list
- [ ] Nguyên liệu scale đúng theo servings
- [ ] Nguyên liệu trùng được merge
- [ ] Check/uncheck items hoạt động
- [ ] Thêm item thủ công
- [ ] Xóa items
- [ ] Nhóm items theo category

### **Thành viên 5 - Meal Plan:**
- [ ] Hiển thị calendar tuần đúng
- [ ] Thêm recipe vào ngày và bữa cụ thể
- [ ] Xóa recipe khỏi meal
- [ ] Navigation giữa các tuần
- [ ] Tạo shopping list từ cả tuần
- [ ] Shopping list tính đúng tổng nguyên liệu
- [ ] Redirect đến Shopping List page sau khi tạo

---

## 📝 Lưu Ý Quan Trọng

### **Cho Thành viên 1 (Setup):**
- Hoàn thành setup trong ngày 1 để team có thể bắt đầu
- Tạo đầy đủ 15 models theo đúng database schema
- CloudinaryService phải hoạt động để các thành viên khác dùng
- Commit và push code sớm

### **Cho tất cả thành viên:**
- Mỗi người làm full-stack module của mình (Backend + Frontend + JavaScript)
- Code phải có validation và error handling
- UI phải responsive (Bootstrap 5)
- Test kỹ trước khi tích hợp
- Commit code thường xuyên
- Viết comment cho code phức tạp
- Không hard-code, dùng configuration

### **SignalR (Thành viên 3):**
- Chỉ dùng cho Comments và Likes real-time
- Các chức năng khác dùng AJAX thông thường
- Test kỹ SignalR connection
- Xử lý trường hợp connection lost

### **Cloudinary:**
- Tất cả ảnh upload lên Cloudinary, không lưu local
- Delete ảnh trên Cloudinary khi xóa recipe/user
- Resize ảnh nếu quá lớn

### **Git Workflow:**
- Branch riêng cho mỗi người: `feature/authentication`, `feature/recipes`, etc.
- Commit thường xuyên với message rõ ràng
- Pull request trước khi merge vào main
- Review code của nhau

---

**Chúc các bạn làm việc hiệu quả! 🚀**