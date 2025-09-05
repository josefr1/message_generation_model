# Message Generation Model

A Python script for generating realistic, context-aware chat messages on a specified topic using the Llama-3.2-3B-Instruct language model. This model simulates social/chat conversations with natural, engaging, and sometimes playful responses, optionally in reply to a previous message.

## 🚀 Features

- **Contextual Generation:** Creates messages based on a topic and an optional previous chat message.
- **Customizable Usernames:** Selects usernames from a provided list for realism.
- **Natural Language Output:** Ensures messages are formatted realistically (e.g., "Username: Message").
- **Validation:** Checks output to ensure it matches expected chat structure.
- **Efficient Inference:** Fast on GPU (T4: ~1s per message).

## 🧩 Main Components

- `create_prompt(...)`: Builds a prompt for the language model, optionally including a previous chat message for continuity.
- `is_valid_message(message)`: Validates the format and length of generated messages.
- `generate_message(...)`: Generates a chat message using the Llama model, with support for optional previous message context.

## 🖥️ Dependencies

- `transformers`
- `torch`
- `huggingface_hub`

Install requirements:
```bash
pip install transformers torch huggingface_hub
```

## 🔑 Setup

1. **Hugging Face Auth:**  
   Log in using your Hugging Face token:
   ```python
   from huggingface_hub import login
   login(token="YOUR_HF_TOKEN")
   ```

2. **Model Weights:**  
   - Text: `meta-llama/llama-3.2-3B-Instruct`

## ⚡ Usage Example

```python
result = generate_message(
    "Mario Run",
    ["player1", "player2", "player3"],
    "hey guys how do you like the game"
)
print(result)
# Output example: player2: I think it's super fun but those jumps are tricky!
```

## 📄 Function Overview

- `create_prompt(title, username_list, previous_message)`
- `is_valid_message(message)`
- `generate_message(title, username_list, previous_message)`

## 📝 Notes

- Modify the username list and style guidelines for your own use case.
- All messages are generated to be engaging, playful, or thoughtfully critical (no toxic output).
- Intended for research, prototyping, and social/chat simulation.

---
MIT License (or specify your own)
