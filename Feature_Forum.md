# Feature_Forum - Forum UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Forum & Community |
| **Test requirement** | Forum Posts, Comments, Categories pages available |
| **Number of TCs** | 16 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 16 | 0 |
| Round 2 | 0 | 0 | 16 | 0 |
| Round 3 | 0 | 0 | 16 | 0 |

---

## Test Cases

### Forum List Page

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FORUM01 | View forum main page | 1. Login<br>2. Navigate to /forum | - Forum header with search<br>- Category filter/tabs<br>- Post list with cards<br>- "Tạo bài viết" button<br>- Sorting options | Logged in |
| FORUM02 | Filter by category | 1. On forum page<br>2. Click category "Kinh nghiệm canh tác" | - Category tab becomes active<br>- Posts filtered by category<br>- Post count updates<br>- "Tất cả" to clear filter | Forum page open |
| FORUM03 | View post card info | 1. On forum page<br>2. Observe a post card | - Post title (truncated if long)<br>- Author name and avatar<br>- Category badge<br>- Date/time posted<br>- Comment and view count | Posts exist |
| FORUM04 | Search forum posts | 1. On forum page<br>2. Type "hữu cơ" in search<br>3. Press Enter | - Results show matching posts<br>- Search term highlighted<br>- "Không tìm thấy" if no match<br>- Clear search option | Forum page open |

---

### Create Forum Post

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FORUM05 | Open create post form | 1. On forum page<br>2. Click "Tạo bài viết" | - Form/modal opens<br>- Title input<br>- Category dropdown<br>- Content rich text editor<br>- Image upload option<br>- Đăng and Hủy buttons | Logged in |
| FORUM06 | Create post - valid data | 1. Open create form<br>2. Enter Title: "Kinh nghiệm trồng rau hữu cơ"<br>3. Select Category: "Kinh nghiệm"<br>4. Enter content (200+ chars)<br>5. Click "Đăng bài" | - Form validates<br>- Loading shows<br>- Success "Đăng bài thành công!"<br>- Redirect to new post<br>- Post in forum list | Form open |
| FORUM07 | Create post - validation | 1. Open create form<br>2. Leave title empty<br>3. Leave content empty<br>4. Click "Đăng bài" | - Inline errors shown<br>- "Tiêu đề là bắt buộc"<br>- "Nội dung là bắt buộc"<br>- Form not submitted | Form open |
| FORUM08 | Post content character limit | 1. Open create form<br>2. Fill title<br>3. Enter content > 10,000 chars | - Character counter shows (9500/10000)<br>- Warning when near limit<br>- Content truncated at max<br>- Error if exceeded | Form open |

---

### Post Detail Page

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FORUM09 | View post detail | 1. On forum list<br>2. Click a post title | - Full post title<br>- Author info with avatar, date<br>- Full content rendered<br>- Images displayed<br>- Like/Share buttons<br>- Comments section | Post exists |
| FORUM10 | Like a post | 1. On post detail<br>2. Click "Thích" button | - Like count increments<br>- Button shows liked state<br>- Click again to unlike<br>- Count updates real-time | Post detail open |

---

### Comments

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FORUM11 | View comment section | 1. On post detail<br>2. Scroll to comments | - Comment input area<br>- User avatar shown<br>- "Bình luận" button<br>- Existing comments listed | Post detail open |
| FORUM12 | Add comment - valid | 1. On post detail<br>2. Type: "Bài viết hay quá!"<br>3. Click "Bình luận" | - Comment submitted<br>- New comment appears<br>- Shows user info and time<br>- Comment count updates<br>- Input cleared | Logged in |
| FORUM13 | Add comment - empty | 1. On post detail<br>2. Leave comment empty<br>3. Click "Bình luận" | - Error "Bình luận không được để trống"<br>- Button disabled when empty<br>- No empty bubble | Post detail open |
| FORUM14 | Delete own comment | 1. On post with own comment<br>2. Click delete icon on comment<br>3. Confirm deletion | - Delete only on own comments<br>- Confirmation dialog<br>- After confirm: Comment removed<br>- Count decrements | Has own comment |

---

### Forum Pagination & Sorting

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FORUM15 | Sort posts | 1. On forum page<br>2. Click sort dropdown<br>3. Select "Phổ biến nhất" | - Sort options: Mới nhất, Phổ biến, Nhiều bình luận<br>- List reorders<br>- Selected shown in dropdown | Multiple posts exist |
| FORUM16 | Forum pagination | 1. On forum (>10 posts)<br>2. Scroll to bottom<br>3. Click page 2 or "Xem thêm" | - Pagination visible<br>- Navigation works<br>- Or infinite scroll loads more<br>- Current page indicated | >10 posts exist |
