# Feature 12: Chatbot Conversations - UI Test Cases

## Sheet Information
| Field | Value |
|-------|-------|
| **Sheet Name** | TC_Chatbot |
| **Feature** | Chatbot & AI Assistant |
| **Module** | Chat Interface, Conversations |
| **Total Test Cases** | 12 |
| **Testing Type** | UI Functional Testing |

---

## Test Cases

### 12.1 Chat Interface Layout

| TC ID | TC_CHAT_001 |
|-------|------------|
| **Description** | Verify chat page main layout |
| **Pre-conditions** | User logged in |
| **Procedure** | 1. Navigate to Chat or Assistant section<br>2. Observe the chat interface |
| **Expected Results** | - Chat window with message area<br>- Input field at bottom<br>- Send button visible<br>- Chat history sidebar (if applicable)<br>- Bot avatar/name displayed |

| TC ID | TC_CHAT_002 |
|-------|------------|
| **Description** | Verify chat welcome message |
| **Pre-conditions** | User opens new chat session |
| **Procedure** | 1. Start new conversation<br>2. Observe initial state |
| **Expected Results** | - Welcome message from bot displayed<br>- "Hello! How can I help you today?"<br>- Suggested quick questions shown<br>- Input field ready for typing |

| TC ID | TC_CHAT_003 |
|-------|------------|
| **Description** | Verify suggested questions display |
| **Pre-conditions** | User on new chat or empty state |
| **Procedure** | 1. Observe suggested questions/prompts<br>2. Click on a suggestion |
| **Expected Results** | - Quick action buttons/chips visible<br>- Examples: "Track my order", "Product questions"<br>- Click populates input field<br>- Or directly sends the question |

### 12.2 Sending Messages

| TC ID | TC_CHAT_004 |
|-------|------------|
| **Description** | Verify send message by Enter key |
| **Pre-conditions** | User on chat page |
| **Procedure** | 1. Type message: "Hello"<br>2. Press Enter key |
| **Expected Results** | - Message sent immediately<br>- User message appears in chat (right side)<br>- Input field cleared<br>- Typing indicator shows bot responding |

| TC ID | TC_CHAT_005 |
|-------|------------|
| **Description** | Verify send message by Send button |
| **Pre-conditions** | User on chat page |
| **Procedure** | 1. Type message: "What products do you sell?"<br>2. Click Send button |
| **Expected Results** | - Message sent successfully<br>- Send button provides feedback (animation)<br>- Message appears in conversation<br>- Bot response follows |

| TC ID | TC_CHAT_006 |
|-------|------------|
| **Description** | Verify empty message prevention |
| **Pre-conditions** | User on chat page |
| **Procedure** | 1. Leave input field empty<br>2. Click Send or press Enter |
| **Expected Results** | - Nothing is sent<br>- Send button disabled when empty<br>- No empty bubble in chat<br>- Focus remains on input |

| TC ID | TC_CHAT_007 |
|-------|------------|
| **Description** | Verify bot response display |
| **Pre-conditions** | User sent a message |
| **Procedure** | 1. Send message: "What are your hours?"<br>2. Wait for bot response |
| **Expected Results** | - Typing indicator while processing<br>- Bot message appears (left side)<br>- Message has bot avatar<br>- Response is formatted properly<br>- Timestamp shown |

### 12.3 Chat History

| TC ID | TC_CHAT_008 |
|-------|------------|
| **Description** | Verify chat history persistence |
| **Pre-conditions** | User has previous conversations |
| **Procedure** | 1. Navigate away from chat page<br>2. Return to chat page<br>3. Observe conversation |
| **Expected Results** | - Previous messages still visible<br>- Scroll to see older messages<br>- No data loss between sessions<br>- Can continue conversation |

| TC ID | TC_CHAT_009 |
|-------|------------|
| **Description** | Verify conversation history sidebar |
| **Pre-conditions** | User has multiple past conversations |
| **Procedure** | 1. Look for conversation list/sidebar<br>2. Click on a past conversation |
| **Expected Results** | - Sidebar shows past conversations<br>- Each entry shows preview text and date<br>- Click loads that conversation<br>- Current conversation highlighted |

| TC ID | TC_CHAT_010 |
|-------|------------|
| **Description** | Verify start new conversation |
| **Pre-conditions** | User on chat page |
| **Procedure** | 1. Click "New Chat" or "+" button<br>2. Observe new conversation |
| **Expected Results** | - Current conversation preserved<br>- New empty chat window opens<br>- Welcome message displayed again<br>- Old conversation accessible in history |

### 12.4 Message Display & Formatting

| TC ID | TC_CHAT_011 |
|-------|------------|
| **Description** | Verify long message display |
| **Pre-conditions** | User on chat page |
| **Procedure** | 1. Send a very long message (500+ characters)<br>2. Observe message bubble |
| **Expected Results** | - Message wraps properly in bubble<br>- No horizontal scroll<br>- Full message readable<br>- Chat area scrolls to show new message |

| TC ID | TC_CHAT_012 |
|-------|------------|
| **Description** | Verify chat auto-scroll to latest message |
| **Pre-conditions** | User scrolled up in conversation |
| **Procedure** | 1. Scroll up in chat history<br>2. Send a new message<br>3. Receive bot response |
| **Expected Results** | - Chat auto-scrolls to new message<br>- Latest messages visible<br>- "Scroll to bottom" button appears when scrolled up<br>- Smooth scroll animation |

---

## Summary
| Status | Count |
|--------|-------|
| Total Test Cases | 12 |
| Priority - High | 5 |
| Priority - Medium | 5 |
| Priority - Low | 2 |
