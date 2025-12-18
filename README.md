 AUTO-REPLY AI CHATBOT (WhatsApp Automation)

*An automated chatbot that reads WhatsApp chat, analyzes the latest message, generates a funny roast-style AI reply, and sends it automatically using screen automation and AI models.*

---

# **FEATURES**

### **1. Automated Chat Interaction**

* Uses **pyautogui** to:

  * Click and open the chat window
  * Drag-select chat messages
  * Paste & send replies
* Works fully hands-free.

### **2. Chat History Analysis**

* Copies chat text using **pyperclip**.
* Reads entire conversation.
* Detects **who sent the last message**.
* If last sender matches the blocked/target user (e.g., **"Rohan Das"** or **"anu"**) ? decides whether to reply.

### **3. AI-Based Humorous Reply Generation**

* Sends chat history to **Gemini / GPT models**.
* Personality prompt:

  * Bold
  * Savage
  * Gen-Z
  * Roast-style humor
* Generates short, funny, in-character responses.

### **4. Clipboard Operations**

* Uses **pyperclip** to:

  * Copy chat
  * Copy AI reply
  * Paste reply into WhatsApp

### **5. Continuous Automation Loop**

* Every cycle:

  * Read chat
  * Analyze
  * Generate reply
  * Send
  * Wait a few seconds
  * Repeat

---

# **WORKFLOW**

### **1. Initialization**

* Bot clicks the **Chrome/WhatsApp icon** (coords like `1405, 1041`).
* Waits for 1 2 seconds so chat loads.

### **2. Chat History Retrieval**

* Moves cursor to chat area (`701, 229` ? `1870, 917`).
* Drag-selects entire conversation.
* Copies using **Ctrl + C**.
* Reads text via clipboard.

### **3. Message Analysis**

* Function `should_reply()`:

  * Splits chat into lines
  * Reads last valid line
  * Extracts sender name from format:
    `[time] Name: message`
  * If sender = blocked/target user ? **return True**
  * Else ? **False** (no reply)

### **4. AI Response Generation**

* If bot should reply:

  * Sends prompt + chat history to **Gemini / GPT-3.5-turbo**
  * Model generates:

    * Funny roast
    * Bold, stylish tone
    * Short Gen-Z style reply

### **5. Sending the Reply**

* Copies AI reply to clipboard.
* Clicks message box (`767, 981`).
* Pastes reply.
* Presses **Enter** to send.

### **6. Loop**

* Wait 5 seconds.
* Repeat entire cycle automatically.

---

# **LIBRARIES USED**

| Library                   | Purpose                                            |
| ------------------------- | -------------------------------------------------- |
| **pyautogui**             | Mouse clicks, movement, dragging, automated typing |
| **time**                  | Delays between actions                             |
| **pyperclip**             | Clipboard copy/paste                               |
| **google.genai / openai** | AI model to generate roast replies                 |
| **Content, Part**         | AI message structure                               |

---

# **INTERNAL PROGRAM LOGIC (SHORT NOTES)**

### **1. Import Libraries**

* Loads automation, clipboard, timing, and AI modules.

### **2. AI Client Setup**

* `genai.Client(api_key=...)` or `openai.api_key`.
* Model: **gemini-2.5-flash** or **GPT-3.5-turbo**.

### **3. should_reply(chat_log)**

* Reads last message.
* Extracts sender name.
* Compares with target (e.g., **"anu"**, **"Rohan Das"**)
* Returns True/False.

### **4. AI Prompt**

* Character-based personality:

  * Savage
  * Sarcastic
  * Cool Gen-Z tone
  * No cringe, no bad words
  * Mix of English + Hindi + Marathi

### **5. Main Loop**

1. Select chat
2. Copy text
3. Analyze
4. Generate AI reply
5. Paste
6. Send
7. Wait

---

# **FULL SYSTEM SUMMARY (Very Short)**

1. **Reads** WhatsApp chat
2. **Checks** who sent last message
3. **Thinks** using Gemini/GPT
4. **Creates roast reply**
5. **Sends automatically**
6. **Repeats forever**


