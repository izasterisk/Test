# Feature_Chatbot - Chatbot UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Chatbot |
| **Test requirement** | Chat page available |
| **Number of TCs** | 5 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 5 | 0 |
| Round 2 | 0 | 0 | 5 | 0 |
| Round 3 | 0 | 0 | 5 | 0 |

---

## Test Cases

### Chat Page (/chat)

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CHAT01 | Open chat page | 1. Login<br>2. Navigate to /chat | - Chat page loads<br>- Sidebar with conversation history<br>- Main chat area<br>- Welcome message from AI<br>- Input field at bottom | Logged in |
| CHAT02 | Send message to chatbot | 1. Go to /chat<br>2. Type "Xin chào" in input<br>3. Press Enter or click Send | - User message appears in chat<br>- Typing indicator shows<br>- AI response appears after delay<br>- Scroll to bottom | Chat page opened |
| CHAT03 | Use suggested question | 1. Go to /chat (new conversation)<br>2. Click on a suggested question button | - Question fills in input or sends directly<br>- AI responds to the question<br>- Suggested questions may hide after first message | New conversation |
| CHAT04 | Create new conversation | 1. Go to /chat<br>2. Click "Tạo cuộc trò chuyện mới" in sidebar | - New conversation created<br>- Chat area clears<br>- Welcome message shows<br>- New conversation in sidebar list | Logged in |
| CHAT05 | View chat history | 1. Go to /chat<br>2. Click on previous conversation in sidebar | - Selected conversation loads<br>- Previous messages displayed<br>- Can continue chatting<br>- Active conversation highlighted | Has previous conversations |
