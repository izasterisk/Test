# Feature 9: Forum - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_Forum |
| **Feature** | Forum & Community |
| **Module** | Forum Posts, Comments, Categories |
| **Total Test Cases** | 16 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 9.1 Forum List Page

| TC ID | TC_FOR_001 |
|-------|------------|
| **Description** | Verify forum main page layout |
| **Pre-conditions** | User logged in |
| **Procedure** | 1. Navigate to Forum section<br>2. Observe the main forum page |
| **Expected Results** | - Page displays forum header with search<br>- Category filter/tabs visible<br>- Post list with cards or rows<br>- "Create New Post" button prominent<br>- Sorting options available |

| TC ID | TC_FOR_002 |
|-------|------------|
| **Description** | Verify forum category filter |
| **Pre-conditions** | User on forum main page |
| **Procedure** | 1. Click on a category tab/filter (e.g., "Farming Tips")<br>2. Observe filtered results |
| **Expected Results** | - Category tab becomes active<br>- Posts filtered to show only selected category<br>- Post count updates<br>- "All" option to clear filter |

| TC ID | TC_FOR_003 |
|-------|------------|
| **Description** | Verify forum post card information |
| **Pre-conditions** | Forum has posts |
| **Procedure** | 1. Observe a post card in the list<br>2. Check displayed information |
| **Expected Results** | - Post title (truncated if long)<br>- Author name and avatar<br>- Category badge<br>- Post date/time<br>- Comment count and view count<br>- Like/reaction count |

| TC ID | TC_FOR_004 |
|-------|------------|
| **Description** | Verify forum search functionality |
| **Pre-conditions** | User on forum page |
| **Procedure** | 1. Type "organic farming" in search box<br>2. Press Enter or click search |
| **Expected Results** | - Search results show matching posts<br>- Search term highlighted in results<br>- "No posts found" if no match<br>- Clear search option available |

### 9.2 Create Forum Post

| TC ID | TC_FOR_005 |
|-------|------------|
| **Description** | Verify create post form layout |
| **Pre-conditions** | User logged in |
| **Procedure** | 1. Click "Create New Post" button<br>2. Observe the form |
| **Expected Results** | - Form/modal opens with fields:<br>- Title input<br>- Category dropdown<br>- Content rich text editor<br>- Image upload option<br>- Post and Cancel buttons |

| TC ID | TC_FOR_006 |
|-------|------------|
| **Description** | Verify create post with valid data |
| **Pre-conditions** | User on create post form |
| **Procedure** | 1. Enter Title: "Best practices for organic rice farming"<br>2. Select Category: "Farming Tips"<br>3. Enter content (200+ characters)<br>4. Click "Post" |
| **Expected Results** | - Form validates successfully<br>- Loading state during submission<br>- Success: "Post created successfully!"<br>- Redirected to new post page<br>- Post appears in forum list |

| TC ID | TC_FOR_007 |
|-------|------------|
| **Description** | Verify create post - validation errors |
| **Pre-conditions** | User on create post form |
| **Procedure** | 1. Leave title empty<br>2. Leave content empty<br>3. Click "Post" |
| **Expected Results** | - Validation errors inline<br>- "Title is required"<br>- "Content is required"<br>- Form does not submit<br>- Error fields highlighted |

| TC ID | TC_FOR_008 |
|-------|------------|
| **Description** | Verify post content character limit |
| **Pre-conditions** | User on create post form |
| **Procedure** | 1. Fill title<br>2. Enter content exceeding limit (e.g., 10,000 chars)<br>3. Observe behavior |
| **Expected Results** | - Character counter shows limit (e.g., 9500/10000)<br>- Warning when approaching limit<br>- Content truncated or blocked at max<br>- Error message if exceeded |

### 9.3 Post Detail Page

| TC ID | TC_FOR_009 |
|-------|------------|
| **Description** | Verify post detail page layout |
| **Pre-conditions** | Forum has at least one post |
| **Procedure** | 1. Click on a post from forum list<br>2. Observe post detail page |
| **Expected Results** | - Full post title displayed<br>- Author info with avatar, name, date<br>- Full content rendered (markdown/HTML)<br>- Images displayed inline<br>- Like/Share buttons<br>- Comments section below |

| TC ID | TC_FOR_010 |
|-------|------------|
| **Description** | Verify post like functionality |
| **Pre-conditions** | User on post detail page |
| **Procedure** | 1. Click "Like" button on post<br>2. Observe like count and button state |
| **Expected Results** | - Like count increments by 1<br>- Button shows "Liked" state (filled icon)<br>- Click again to unlike<br>- Count updates in real-time |

### 9.4 Comments

| TC ID | TC_FOR_011 |
|-------|------------|
| **Description** | Verify comment input display |
| **Pre-conditions** | User on post detail page |
| **Procedure** | 1. Scroll to comments section<br>2. Observe comment input area |
| **Expected Results** | - Text area for new comment<br>- User avatar next to input<br>- "Post Comment" button<br>- Character limit indicator |

| TC ID | TC_FOR_012 |
|-------|------------|
| **Description** | Verify add comment with valid text |
| **Pre-conditions** | User on post detail page |
| **Procedure** | 1. Type comment: "Great tips! I'll try this on my farm."<br>2. Click "Post Comment" |
| **Expected Results** | - Comment submitted<br>- New comment appears at top/bottom of list<br>- Comment shows user info and timestamp<br>- Comment count updates<br>- Input cleared |

| TC ID | TC_FOR_013 |
|-------|------------|
| **Description** | Verify comment validation - empty |
| **Pre-conditions** | User on post detail page |
| **Procedure** | 1. Leave comment field empty<br>2. Click "Post Comment" |
| **Expected Results** | - Validation error: "Comment cannot be empty"<br>- Button may be disabled when empty<br>- Form does not submit |

| TC ID | TC_FOR_014 |
|-------|------------|
| **Description** | Verify delete own comment |
| **Pre-conditions** | User has posted a comment |
| **Procedure** | 1. Find own comment<br>2. Click delete icon/option<br>3. Confirm deletion |
| **Expected Results** | - Delete option visible only on own comments<br>- Confirmation dialog appears<br>- After confirm: Comment removed<br>- Comment count decrements |

### 9.5 Forum Pagination & Sorting

| TC ID | TC_FOR_015 |
|-------|------------|
| **Description** | Verify forum post sorting options |
| **Pre-conditions** | Forum has multiple posts |
| **Procedure** | 1. Click sort dropdown<br>2. Select "Most Recent"<br>3. Select "Most Popular" |
| **Expected Results** | - Sort options: Most Recent, Most Popular, Most Comments<br>- List reorders based on selection<br>- Selected option shown in dropdown<br>- URL may update with sort param |

| TC ID | TC_FOR_016 |
|-------|------------|
| **Description** | Verify forum pagination |
| **Pre-conditions** | Forum has >10 posts |
| **Procedure** | 1. Scroll to bottom of post list<br>2. Click page 2 or "Load More"<br>3. Navigate through pages |
| **Expected Results** | - Pagination controls visible<br>- Page navigation works correctly<br>- Or infinite scroll loads more<br>- Current page indicated |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 16 |
| Priority - High | 7 |
| Priority - Medium | 6 |
| Priority - Low | 3 |
