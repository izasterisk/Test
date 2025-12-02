# Feature_Forum - Forum UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Forum |
| **Test requirement** | Forum page, Forum detail page available |
| **Number of TCs** | 6 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 6 | 0 |
| Round 2 | 0 | 0 | 6 | 0 |
| Round 3 | 0 | 0 | 6 | 0 |

---

## Test Cases

### Forum Page (/forum)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FORUM01 | View forum post list | 1. Navigate to /forum page | - Loading spinner shows first<br>- Post cards displayed in grid<br>- Each post shows: title, preview image, date<br>- Pagination at bottom<br>- "Đăng Bài Viết Mới" button visible | Page loaded |
| FORUM02 | Navigate forum pagination | 1. Go to /forum<br>2. Click page 2 in pagination<br>3. Click "Trước" button<br>4. Click "Sau" button | - Page changes smoothly<br>- Posts update<br>- Current page highlighted<br>- Scroll to top on page change | Multiple pages exist |
| FORUM03 | Create new forum post | 1. Login<br>2. Go to /forum<br>3. Click "Đăng Bài Viết Mới"<br>4. Fill form:<br>- Title<br>- Select category<br>- Add text content<br>- Add images (optional)<br>5. Click submit | - Create post form/section shows<br>- Category dropdown works<br>- Text editor works<br>- Image upload works<br>- Success toast "Đăng bài viết thành công"<br>- New post appears in list | Logged in |

---

### Forum Detail Page (/forum/:id)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FORUM04 | View post detail | 1. Go to /forum<br>2. Click on any post card | - Navigate to /forum/{id}<br>- Post title displays<br>- Full content shows (text + images)<br>- Author info visible<br>- Comments section visible | Post exists |
| FORUM05 | Add comment to post | 1. Login<br>2. Go to post detail page<br>3. Scroll to comment section<br>4. Enter comment text<br>5. Click "Gửi" or submit | - Comment input shows<br>- Submit button works<br>- Loading on submit<br>- New comment appears in list<br>- Comment count updates | Logged in |
| FORUM06 | View empty forum state | 1. Go to /forum when no posts exist | - Empty state message shows<br>- "Chưa có bài viết nào" message<br>- Illustration/icon for empty state | No posts in database |
