# Feature_Chatbot - Chatbot Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Chatbot |
| **Test requirement** | API and design are available |
| **Number of TCs** | 8 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 8 | 0 |
| Round 2 | 0 | 0 | 8 | 0 |
| Round 3 | 0 | 0 | 8 | 0 |

---

## Test Cases

### Conversation Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CHAT01 | Create new conversation | 1. Login<br>2. Call POST `/api/ChatbotConversation`<br>3. Send first message | - Conversation created<br>- First message saved<br>- AI response generated<br>- Status 201 Created | Logged in |
| CHAT02 | Get all conversations | 1. Login<br>2. Call GET `/api/ChatbotConversation?page=1&pageSize=10` | - List of user's conversations<br>- Ordered by recent<br>- Status 200 OK | Logged in |
| CHAT03 | Update conversation | 1. Login<br>2. Call PATCH `/api/ChatbotConversation/{conversationId}`<br>3. Update title or is_active | - Conversation updated<br>- Status 200 OK | Conversation exists |

---

### Message Management

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CHAT04 | Send message to existing conversation | 1. Login<br>2. Call POST `/api/ChatbotConversation/{conversationId}/message`<br>3. Send message content | - Message saved<br>- AI response generated<br>- Status 201 Created | Conversation exists |
| CHAT05 | Get messages in conversation | 1. Login<br>2. Call GET `/api/ChatbotConversation/{conversationId}/messages?page=1` | - List of messages returned<br>- Ordered chronologically<br>- Status 200 OK | Conversation with messages |
| CHAT06 | Send empty message | 1. Login<br>2. Call POST `/api/ChatbotConversation/{conversationId}/message`<br>3. Send empty content | - Validation error<br>- Status 400 Bad Request | Conversation exists |

---

### Edge Cases

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CHAT07 | Access other user's conversation | 1. Login as User A<br>2. Try to send message to User B's conversation | - Error: Unauthorized<br>- Status 403 Forbidden | Different user's conversation |
| CHAT08 | Send message to inactive conversation | 1. Login<br>2. Conversation is_active = false<br>3. Try to send message | - Error or reactivate conversation<br>- Behavior as designed | Inactive conversation |
