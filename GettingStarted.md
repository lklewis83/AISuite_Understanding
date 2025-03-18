# 🛠️ **AISuite Python Package Documentation**
https://github.com/andrewyng/aisuite/blob/main/README.md

**Version:** 0.1.10

**Original Authors:** Andrew Ng, Rohit P

**Editor:** Lani Lewis


## 📌 **Installation**
To install `aisuite` with all dependencies:  
`!pip install aisuite[all]`

---

## 📦 **AISuite Package Overview**
The `aisuite` package consists of the following modules and subpackages:

### **Modules**
- `client` – Manages client-side interactions.
- `provider` – Handles data retrieval and processing.
- `utils` – Contains helper functions and utilities.

### **Subpackages**
- `framework` – Provides core functionalities.
- `providers` – Supports multiple data providers.

---

## 🛠 **AISuite Client Module**
### 📌 **Module Information**
- **Module Name:** `aisuite.client`
- **File Location:** `/usr/local/lib/python3.11/dist-packages/aisuite/client.py`

### **Classes in `aisuite.client`**

#### **Client / Chat Usage**  
#### `Chat`
- **Purpose:** Manages chat interactions.

The `client.chat.completions.create` method is used to send messages to the model and receive responses.

### _**Standard Roles in Message Structures**_  
Messages sent to the model must include a **role** that defines their purpose in the conversation. The three primary roles used in **AISuite, OpenAI, and other LLM-based APIs** are:

##### **1️⃣ System Role (`"role": "system"`)**  
- Provides **global instructions** for how the model should behave.  
- Used for **setting constraints, response style, or persona guidance** (e.g., *"Respond in Shakespearean."*).  

##### **2️⃣ User Role (`"role": "user"`)**  
- Represents the **actual input** from the human interacting with the model.  
- Used for **asking questions, giving prompts, or providing instructions** (e.g., *"Tell me a joke."*).  

##### **3️⃣ Assistant Role (`"role": "assistant"`)**  
- Represents the **AI model’s response** to the user.  
- Used in **multi-turn conversations** to retain context and reference previous answers.  

### _**What is Content in Message Structures?**_  
Each message must include a `"content"` field, which represents the **actual text** the role is providing.  

- **For system messages**, content defines behavior or style (e.g., *"You are a helpful assistant."*).  
- **For user messages**, content contains the user’s input (e.g., *"What is the capital of France?"*).  
- **For assistant messages**, content stores the AI’s response (e.g., *"The capital of France is Paris."*).  

### _**Temperature Values**_
- **Lower values (0.2 - 0.4):** Produce more **focused, deterministic** responses.
- **Higher values (0.7 - 0.9):** Encourage more **creative, varied** outputs.

#### *Message Structure Suggestions*
Messages sent to the model should be formatted properly based on the intended usage. Below are three suggested structures:

- **Basic Option:** A simple structure where the model is given a system instruction.  

_messages = [{"role": "system", "content": "Respond in Shakespearean"}]_

- **No History Option:** Includes an initial system instruction and a direct user prompt.  

_messages = [{"role": "system", "content": "Respond in Shakespearean"},
                {"role": "user", "content": "Tell me a joke."}]_

- **History Option:** Includes an instruction, a user prompt, and the assistant's previous response to maintain conversation context. 

_messages = [{"role": "system", "content": "Respond in Shakespearean"}, 
                {"role": "user", "content": "Tell me a joke."},
                {"role": "assistant", "content": history[0]}]_

Each structure can be adapted based on the specific requirements of the conversation.

---

## 🛠 **AISuite Provider Module**
### 📌 **Module Information**
- **Module Name:** `aisuite.provider`
- **File Location:** `/usr/local/lib/python3.11/dist-packages/aisuite/provider.py`

### **Classes in `aisuite.provider`**
#### `LLMError`
- **Purpose:** Custom exception class for handling LLM-related errors.

---

## 🛠 **AISuite Utilities Module**
### 📌 **Package Information**
- **Package Name:** `aisuite.utils`
- **File Location:** `(built-in)`

### 📂 **Contents of `aisuite.utils`**
#### `tools`
- **Purpose:** Contains utility functions and helper methods.

#### 📜 **AISuite Utility: `aisuite.utils.tools`**
##### 📌 **Module Information**
- **Module Name:** `aisuite.utils.tools`
- **File Location:** `/usr/local/lib/python3.11/dist-packages/aisuite/utils/tools.py`

##### **Classes in `aisuite.utils.tools`**
###### `Tools`
- **Purpose:** Manages and executes registered tools based on model tool calls.
