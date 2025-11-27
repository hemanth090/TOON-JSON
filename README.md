# TOON Data & Token Studio

**Compare TOON vs JSON for Token Efficiency**

A Streamlit application for converting between JSON and TOON formats, querying data with Gemini AI, and monitoring token usage with LangSmith observability.

## Features

- **Format Conversion**: Bidirectional JSON ↔ TOON conversion
- **AI-Powered Queries**: Ask questions about your data using Google Gemini
- **Token Tracking**: Monitor and compare token efficiency between formats
- **LangSmith Integration**: Full observability with separate project tracking for JSON and TOON queries
- **Real-time Metrics**: View token usage for every operation

## What is TOON?

TOON is a compact, human-readable serialization format optimized for LLM contexts. It significantly reduces token usage compared to JSON while maintaining readability.

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/hemanth090/TOON-JSON.git
   cd TOON-JSON
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**
   
   Copy `.env.example` to `.env` and add your API keys:
   ```bash
   cp .env.example .env
   ```
   
   Edit `.env` and add:
   ```
   GEMINI_API_KEY=your_gemini_api_key_here
   LANGSMITH_API_KEY=your_langsmith_api_key_here
   LANGSMITH_TRACING=true
   ```

## Getting API Keys

### Google Gemini API Key
1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Create a new API key
4. Copy and paste into `.env`

### LangSmith API Key (Optional)
1. Visit [LangSmith Settings](https://smith.langchain.com/settings)
2. Sign in or create an account
3. Navigate to "API Keys"
4. Create a new API key
5. Copy and paste into `.env`

## Usage

Run the Streamlit app:
```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`

## Features Overview

### 1. JSON to TOON Conversion
- Paste JSON data
- Configure indent size and delimiter
- View token savings percentage
- Copy TOON output

### 2. TOON to JSON Conversion
- Paste TOON data
- Convert back to JSON format
- View token comparison

### 3. Query & Analysis
- Paste JSON or TOON data
- Ask natural language questions
- Get AI-powered answers from Gemini
- View input/output token usage
- All queries logged to LangSmith

## LangSmith Projects

Queries are automatically logged to separate LangSmith projects:
- `json-query` - Queries on JSON data
- `toon-query` - Queries on TOON data

## Project Structure

```
.
├── app.py                 # Main Streamlit application
├── requirements.txt       # Python dependencies
├── .env.example          # Environment variable template
├── .gitignore            # Git ignore rules
├── LANGSMITH_SETUP.md    # LangSmith setup guide
└── README.md             # This file
```

## Dependencies

- `streamlit` - Web application framework
- `toon_format` - TOON format encoder/decoder
- `tiktoken` - Token counting (OpenAI tokenizer)
- `langsmith` - LangSmith observability
- `python-dotenv` - Environment variable management
- `google-generativeai` - Google Gemini AI SDK

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `GEMINI_API_KEY` | Yes | Google Gemini API key for AI queries |
| `LANGSMITH_API_KEY` | No | LangSmith API key for observability |
| `LANGSMITH_TRACING` | No | Enable LangSmith tracing (default: true) |

## Security Notes

- Never commit `.env` file to Git
- Keep your API keys secure
- Use `.env.example` as a template only
- The `.gitignore` file prevents accidental commits of sensitive data

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Author

[Hemanth](https://github.com/hemanth090)

## Acknowledgments

- [TOON Format](https://github.com/toon-format/toon-format) - Compact serialization format
- [LangSmith](https://smith.langchain.com/) - LLM observability platform
- [Google Gemini](https://ai.google.dev/) - AI model for data analysis
