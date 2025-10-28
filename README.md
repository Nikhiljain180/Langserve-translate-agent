# LangChain Translation Server (LECL)

A simple translation API server built with LangChain and FastAPI that provides a RESTful interface for language translation using OpenAI's GPT models.

## Features

- 🌍 Multi-language translation support
- 🚀 FastAPI-based REST API
- 🔗 LangChain integration for AI workflows
- 📦 Easy-to-use translation chain

## Prerequisites

- Python 3.12 or higher
- OpenAI API key

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Nikhiljain180/Langserve-translate-agent.git
cd Langserve-translate-agent
```

2. Install dependencies:
```bash
pip install -r requirement.txt
```

Or using uv:
```bash
uv sync
```

3. Set up environment variables:
```bash
cp .env.example .env
```

Edit `.env` and add your OpenAI API key:
```
OPENAI_API_KEY=your_api_key_here
```

## Usage

### Running the Server

Start the development server:
```bash
python main.py
```

Or with uvicorn directly:
```bash
uvicorn main:app --reload
```

The server will start at `http://127.0.0.1:8000`

### API Endpoints

#### Translate Text

**POST** `/chain/invoke`

Request body:
```json
{
  "input": {
    "text": "Hello, how are you?",
    "language": "Spanish"
  }
}
```

Response:
```json
{
  "output": "Hola, ¿cómo estás?"
}
```

### API Documentation

Once the server is running, access the interactive API documentation at:
- Swagger UI: `http://127.0.0.1:8000/docs`
- ReDoc: `http://127.0.0.1:8000/redoc`

## Configuration

### Supported Languages

You can translate to any language. Simply specify the target language in the request:
- English
- Spanish
- French
- German
- Japanese
- Chinese
- And many more...

### Environment Variables

- `OPENAI_API_KEY`: Your OpenAI API key (required)
- `LANGSMITH_TRACING`: Enable/disable LangSmith tracing (optional, default: false)
- `LANGSMITH_API_KEY`: LangSmith API key for tracing (optional)
- `LANGSMITH_ENDPOINT`: LangSmith endpoint URL (optional)
- `LANGSMITH_PROJECT`: Project name for LangSmith (optional)

## Architecture

The application uses:
- **FastAPI**: Web framework for the API
- **LangChain**: AI orchestration framework
- **LangServe**: Adds production-ready endpoints for LangChain chains
- **OpenAI GPT-4o-mini**: Translation model

### Chain Structure

```
Prompt Template → OpenAI Model → Output Parser
```

## Development

### Project Structure

```
LECL/
├── main.py              # Main application file
├── requirement.txt      # Python dependencies
├── pyproject.toml       # Project configuration
├── .env.example         # Environment variables template
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - see [LICENSE](LICENSE) file for details

## Author

Nikhil Jain

## Acknowledgments

- Built with [LangChain](https://www.langchain.com/)
- Powered by [OpenAI](https://openai.com/)
- Deployed with [FastAPI](https://fastapi.tiangolo.com/)
