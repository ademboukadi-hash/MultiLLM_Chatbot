# Multi-LLM Chatbot

A small Streamlit chatbot that lets you chat with either local Ollama models or the Groq cloud model provider.

## Features

- Choose between Ollama and Groq Cloud from the sidebar
- Switch between available models
- Keep a short conversation memory summary to reduce token usage over time
- Display previous messages in the chat UI
- Store conversation state in the Streamlit session

## Project structure

- `app.py` – main Streamlit application
- `requirements.txt` – Python dependencies
- `.env` – environment variables for API keys

## Requirements

- Python 3.10+
- Ollama installed locally if you want to use local models
- A Groq API key if you want to use Groq Cloud

## Installation

1. Create and activate a virtual environment:

   ```bash
   python -m venv .venv
   .venv\Scripts\activate
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Configure environment variables in a `.env` file:

   ```env
   GROQ_API_KEY=your_groq_api_key_here
   ```

4. Start Ollama and make sure the models are available locally if needed.

## Run the app

```bash
streamlit run app.py
```

Then open the local URL displayed by Streamlit in your browser.

## Supported providers

### Ollama

The app uses local model names such as:

- `qwen3:1.7b`
- `gemma3:4b`
- `llama3.1:8b`

Make sure these models are pulled and available in your Ollama installation.

### Groq Cloud

The app uses the Groq API with:

- `openai/gpt-oss-20b`

A valid `GROQ_API_KEY` is required.

## Notes

- The app resets the chat history when the selected model or provider changes.
- The conversation is summarized periodically to keep context lighter while preserving key information.
