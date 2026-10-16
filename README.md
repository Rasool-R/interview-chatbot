# Interview Chatbot

A Streamlit app that simulates a job interview with an AI interviewer and gives you feedback at the end. You enter your background, choose a role and a company, answer the interviewer's questions, and receive a score with feedback on your performance.

## How It Works

1. **Setup**: enter your name, experience, and skills, then pick a level (Junior / Mid-level / Senior), a position, and a company.
2. **Interview**: the app builds a system prompt from your choices and the model plays an HR interviewer. Replies are streamed in real time.
3. **Feedback**: after 5 answers, a separate model call reviews the whole conversation and returns an overall score and written feedback.
4. **Restart**: one click reloads the app for a new interview.

## Features

- Tailored interviews: level, position, and company are injected into the prompt
- Positions: Data Scientist, Data Engineer, ML Engineer, BI Analyst, Financial Analyst
- Streaming chat UI built with `st.chat_message` and `st.write_stream`
- Works with OpenAI or any OpenAI-compatible API (custom base URL)

## Getting Started

**1. Install dependencies**

```bash
pip install -r requirements.txt
```

**2. Add your credentials** in `.streamlit/secrets.toml`

```toml
OPENAI_API_KEY = "your_key"
OPENAI_API_URL = "https://api.openai.com/v1"  # or any compatible endpoint
OPENAI_MODEL   = "gpt-4o"
```

**3. Run the app**

```bash
streamlit run app.py
```

> Never commit `secrets.toml`. Add `.streamlit/secrets.toml` to your `.gitignore`.

## Project Structure

```
interview-chatbot/
├── app.py              # The whole app: setup form, chat, feedback
├── requirements.txt
└── .streamlit/
    └── secrets.toml    # API credentials (keep private)
```

## Tech Stack

Python · Streamlit · OpenAI API · streamlit-js-eval
