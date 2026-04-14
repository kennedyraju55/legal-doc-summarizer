# 📜 Legal Document Summarizer

> AI-powered legal document analysis and automatic summarization using advanced LLMs

[![Python 3.11+](https://img.shields.io/badge/Python-3.11+-blue?style=for-the-badge&logo=python)](https://www.python.org/) [![License: MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE) [![Gemma 4](https://img.shields.io/badge/Gemma-4-orange?style=for-the-badge&logo=google)](https://deepmind.google/gemma/) [![Privacy First](https://img.shields.io/badge/Privacy-First-red?style=for-the-badge&logo=shield)](https://en.wikipedia.org/wiki/Privacy) [![Ollama](https://img.shields.io/badge/Ollama-Enabled-blueviolet?style=for-the-badge)](https://ollama.ai)

---

## 🚀 Quick Start

### Prerequisites
- Python 3.11 or higher
- pip (Python package manager)
- Ollama installed and running locally
- 8GB+ RAM recommended

### Installation

\\\ash
# Clone the repository
git clone https://github.com/kennedyraju55/legal-doc-summarizer.git
cd legal-doc-summarizer

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Ensure Ollama is running
ollama pull gemma:latest
ollama serve
\\\

### Running

\\\ash
# Start the server
python -m uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

# Visit API documentation
# http://localhost:8000/docs
\\\

---

## 🏗️ Architecture

\\\
┌─────────────────────────────────────────────────────┐
│                   User Interface                     │
│         (Web Dashboard / API Client)                │
└────────────────────┬────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────┐
│              FastAPI Web Server                      │
│          (REST API Endpoints)                        │
└────────────────────┬────────────────────────────────┘
                     │
         ┌───────────┼───────────┐
         ▼           ▼           ▼
    ┌────────┐ ┌────────┐ ┌─────────┐
    │ Input  │ │ Process│ │ Storage │
    │Handler │ │Engine  │ │ Layer   │
    └────┬───┘ └───┬────┘ └─────────┘
         │         │
         └────┬────┘
              ▼
    ┌─────────────────────┐
    │  Ollama / Gemma 4   │
    │  (Local LLM)        │
    └─────────────────────┘
\\\

---

## ⭐ Key Features

- ✅ Automatic legal document parsing and text extraction
- ✅ Intelligent summarization using Gemma 4 and Ollama
- ✅ Privacy-first architecture with local model execution
- ✅ Batch processing for multiple documents
- ✅ Customizable summary length and detail level
- ✅ Support for PDF, DOCX, and TXT formats
- ✅ Export summaries in multiple formats
- ✅ Performance metrics and token usage tracking
- ✅ Multi-language document support
- ✅ RESTful API for integration

---

## 🛠️ Tech Stack

| Technology | Purpose |
|-----------|---------|
| Python 3.11+ | Core programming language |
| FastAPI | High-performance web framework |
| Ollama | Local LLM inference engine |
| Gemma 4 | Advanced language model |
| PDFPlumber | PDF extraction library |
| LangChain | LLM orchestration framework |

---

## 📁 Project Structure

\\\
legal-doc-summarizer/
├── app/
│   ├── __init__.py
│   ├── main.py              # FastAPI application
│   ├── models.py            # Data models and schemas
│   ├── routes/              # API endpoints
│   ├── services/            # Business logic
│   └── utils/               # Helper functions
├── tests/                   # Unit and integration tests
├── docs/                    # Documentation
├── requirements.txt         # Python dependencies
├── .env.example            # Environment variables template
├── Dockerfile              # Container configuration
└── README.md               # This file
\\\

---

## 🔐 Privacy & Security

This project prioritizes privacy and security:
- **Local Processing**: All data is processed locally using Ollama
- **No Cloud Uploads**: Your documents never leave your machine
- **Open Source**: Fully transparent codebase for security audits
- **MIT Licensed**: Free for personal and commercial use

---

## 📖 Usage Examples

\\\python
import requests

# API endpoint
BASE_URL = "http://localhost:8000"

# Example request
response = requests.post(
    f"{BASE_URL}/process",
    files={"file": open("document.pdf", "rb")},
    json={"options": {"detail_level": "high"}}
)

print(response.json())
\\\

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (\git checkout -b feature/amazing-feature\)
3. Commit your changes (\git commit -m 'Add amazing feature'\)
4. Push to the branch (\git push origin feature/amazing-feature\)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Kennedy Raju**

- GitHub: [@kennedyraju55](https://github.com/kennedyraju55)
- Dev.to: [@kennedyraju55](https://dev.to/kennedyraju55)
- LinkedIn: [Kennedy Raju Guthikonda](https://www.linkedin.com/in/nrk-raju-guthikonda-504066a8)

---

## 📞 Support

If you have questions or need help:
1. Check the [Documentation](./docs)
2. Search [GitHub Issues](https://github.com/kennedyraju55/legal-doc-summarizer/issues)
3. Create a new [Issue](https://github.com/kennedyraju55/legal-doc-summarizer/issues/new)

---

## 🙏 Acknowledgments

- [Ollama](https://ollama.ai) - Local LLM infrastructure
- [Google Gemma](https://deepmind.google/gemma/) - Language models
- [FastAPI](https://fastapi.tiangolo.com/) - Web framework
- All contributors and supporters

---

**Made with ❤️ by Kennedy Raju**