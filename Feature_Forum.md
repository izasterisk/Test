# Feature_Forum - Forum Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Forum |
| **Test requirement** | API and design are available |
| **Number of TCs** | 14 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 14 | 0 |
| Round 2 | 0 | 0 | 14 | 0 |
| Round 3 | 0 | 0 | 14 | 0 |

---

## Test Cases

### Forum Category

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FORUM01 | Get all forum categories | 1. Call GET `/api/ForumCategory` | - List of categories returned<br>- Status 200 OK | Categories exist |
| FORUM02 | Create forum category | 1. Login<br>2. Call POST `/api/ForumCategory`<br>3. Send category name | - Category created<br>- Status 201 Created | Logged in |

---

### Forum Post

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FORUM03 | Get all forum posts | 1. Call GET `/api/ForumPost?page=1&pageSize=10` | - List of posts returned<br>- Pagination info | Posts exist |
| FORUM04 | Get posts by category | 1. Call GET `/api/ForumPost/category/{categoryId}` | - Only posts in category returned | Category has posts |
| FORUM05 | Get post detail | 1. Call GET `/api/ForumPost/{id}` | - Post detail with content blocks<br>- Images included | Post exists |
| FORUM06 | Create forum post | 1. Login<br>2. Call POST `/api/ForumPost` (multipart)<br>3. Send title, content, images | - Post created<br>- Images uploaded<br>- Status 200 OK | Logged in |
| FORUM07 | Update forum post | 1. Login as post owner<br>2. Call PUT `/api/ForumPost/{id}`<br>3. Update content | - Post updated<br>- Status 200 OK | Own post exists |
| FORUM08 | Delete forum post | 1. Login as post owner<br>2. Call DELETE `/api/ForumPost/{id}` | - Post deleted<br>- Status 200 OK | Own post exists |
| FORUM09 | Like forum post | 1. Login<br>2. Call POST `/api/ForumPost/{id}/like` | - Like count increased<br>- Status 200 OK | Post exists |
| FORUM10 | Increase view count | 1. Call POST `/api/ForumPost/{id}/view` | - View count increased<br>- Status 200 OK | Post exists |

---

### Forum Comment

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| FORUM11 | Get post with comments | 1. Call GET `/api/ForumPost/{id}/with-comments` | - Post with all comments returned | Post has comments |
| FORUM12 | Create comment | 1. Login<br>2. Call POST `/api/ForumComment`<br>3. Send post ID, content | - Comment created<br>- Status 201 Created | Logged in, post exists |
| FORUM13 | Reply to comment | 1. Login<br>2. Call POST `/api/ForumComment`<br>3. Send parent comment ID | - Reply created<br>- Nested under parent | Parent comment exists |
| FORUM14 | Delete comment | 1. Login as comment owner<br>2. Call DELETE `/api/ForumComment/{id}` | - Comment deleted<br>- Status 200 OK | Own comment exists |
