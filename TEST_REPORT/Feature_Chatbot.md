# Feature_Chatbot - Chatbot UI Test Cases

## Sheet Information

| Field | Value |
|-------|-------|
| **Feature** | Chatbot & AI Assistant |
| **Test requirement** | Chat Interface, Conversations pages available |
| **Number of TCs** | 12 |

## Testing Round Summary

| Testing Round | Passed | Failed | Pending | N/A |
|---------------|--------|--------|---------|-----|
| Round 1 | 0 | 0 | 12 | 0 |
| Round 2 | 0 | 0 | 12 | 0 |
| Round 3 | 0 | 0 | 12 | 0 |

---

## Test Cases

### Chat Interface Layout

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CHAT01 | View chat page layout | 1. Login<br>2. Navigate to /chat or Assistant | - Chat window with message area<br>- Input field at bottom<br>- Send button visible<br>- History sidebar (if applicable)<br>- Bot avatar/name displayed | Logged in |
| CHAT02 | Welcome message display | 1. Start new chat session<br>2. Observe initial state | - Welcome message from bot<br>- "Xin chào! Tôi có thể giúp gì?"<br>- Suggested quick questions shown<br>- Input field ready | New session |
| CHAT03 | Suggested questions | 1. On new chat/empty state<br>2. Observe suggestions<br>3. Click a suggestion | - Quick action chips visible<br>- Examples: "Theo dõi đơn hàng", "Hỏi về sản phẩm"<br>- Click populates input<br>- Or sends directly | Chat page open |

---

### Sending Messages

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CHAT04 | Send message by Enter | 1. On chat page<br>2. Type: "Xin chào"<br>3. Press Enter | - Message sent immediately<br>- User message appears (right side)<br>- Input cleared<br>- Typing indicator shows | Chat page open |
| CHAT05 | Send message by button | 1. On chat page<br>2. Type: "Bạn bán những gì?"<br>3. Click Send button | - Message sent<br>- Button provides feedback<br>- Message in conversation<br>- Bot response follows | Chat page open |
| CHAT06 | Empty message prevention | 1. On chat page<br>2. Leave input empty<br>3. Click Send or Enter | - Nothing sent<br>- Send button disabled when empty<br>- No empty bubble<br>- Focus stays on input | Chat page open |
| CHAT07 | Bot response display | 1. Send: "Giờ làm việc?"<br>2. Wait for response | - Typing indicator while processing<br>- Bot message appears (left side)<br>- Message has bot avatar<br>- Response formatted properly<br>- Timestamp shown | Message sent |

---

### Chat History

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CHAT08 | Chat history persistence | 1. Have a conversation<br>2. Navigate away<br>3. Return to chat | - Previous messages visible<br>- Scroll to see older<br>- No data loss<br>- Can continue conversation | Has chat history |
| CHAT09 | Conversation history sidebar | 1. Look for sidebar<br>2. Click past conversation | - Sidebar shows past chats<br>- Preview text and date<br>- Click loads conversation<br>- Current chat highlighted | Multiple conversations |
| CHAT10 | Start new conversation | 1. On chat page<br>2. Click "Cuộc trò chuyện mới" | - Current conversation preserved<br>- New empty chat opens<br>- Welcome message again<br>- Old chat in history | Chat page open |

---

### Message Display

| Test Case ID | Test Case Description | Test Case Procedure | Expected Results | Pre-conditions |
|--------------|----------------------|---------------------|------------------|----------------|
| CHAT11 | Long message display | 1. Send long message (500+ chars)<br>2. Observe bubble | - Message wraps in bubble<br>- No horizontal scroll<br>- Full message readable<br>- Chat scrolls to new message | Chat page open |
| CHAT12 | Auto-scroll to latest | 1. Scroll up in history<br>2. Send new message<br>3. Receive bot response | - Chat auto-scrolls to new<br>- Latest messages visible<br>- "Scroll to bottom" button when scrolled up<br>- Smooth scroll animation | Has chat history |
