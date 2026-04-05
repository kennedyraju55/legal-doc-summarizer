<div align="center">
<img src="https://img.shields.io/badge/⚖️_Legal_Doc_Summarizer-Local_LLM_Powered-blue?style=for-the-badge&labelColor=1a1a2e&color=16213e" alt="Project Banner" width="600"/>

<br/>

<img src="https://img.shields.io/badge/Gemma_4-Ollama-orange?style=flat-square&logo=google&logoColor=white" alt="Gemma 4"/>
<img src="https://img.shields.io/badge/Python-3.9+-blue?style=flat-square&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/Streamlit-Web_UI-red?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>
<img src="https://img.shields.io/badge/Click-CLI-green?style=flat-square&logo=gnu-bash&logoColor=white" alt="Click CLI"/>
<img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" alt="License"/>

<br/><br/>

<strong>Part of <a href="https://github.com/kennedyraju55/90-local-llm-projects">90 Local LLM Projects</a> collection</strong>

</div>

<br/>
# 📜 Legal Document Summarizer

![Python](https://img.shields.io/badge/Python-3.11+-blue?logo=python&logoColor=white)
![LLM](https://img.shields.io/badge/LLM-Gemma%204-orange)
![Ollama](https://img.shields.io/badge/Ollama-Local-green)
![Streamlit](https://img.shields.io/badge/UI-Streamlit-red?logo=streamlit)
![License](https://img.shields.io/badge/License-MIT-yellow)

Production-grade legal document analysis tool that summarizes contracts, agreements, and legal documents using a local LLM via Ollama. Features multi-document comparison, clause extraction, risk scoring, and PDF-ready markdown export.

## ✨ Features

- **Multi-format input** — Supports PDF and text files
- **Key information extraction** — Parties, clauses, obligations, dates, termination conditions, penalties
- **Clause extraction** — Categorized clause analysis with risk levels
- **Risk scoring** — Financial, termination, IP, compliance, and confidentiality risk assessment
- **Multi-document comparison** — Side-by-side analysis of multiple legal documents
- **PDF-ready export** — Generate comprehensive markdown reports
- **Dual interface** — CLI for power users, Streamlit Web UI for visual analysis
- **Configurable** — YAML config + environment variable overrides
- **Local & private** — All processing runs locally via Ollama

## 🚀 Installation

```bash
cd 11-legal-doc-summarizer
pip install -r requirements.txt
```

Make sure [Ollama](https://ollama.ai) is installed and running:

```bash
ollama serve
ollama pull gemma4
```

## 📋 CLI Usage

```bash
# Summarize a document
python -m src.legal_summarizer.cli summarize --file contract.pdf

# Narrative format with export
python -m src.legal_summarizer.cli summarize --file agreement.txt --format narrative --export report.md

# Extract clauses
python -m src.legal_summarizer.cli clauses --file contract.pdf

# Risk assessment
python -m src.legal_summarizer.cli risks --file lease.pdf

# Compare multiple documents
python -m src.legal_summarizer.cli compare --files doc1.txt --files doc2.txt

# Full export report
python -m src.legal_summarizer.cli export --file contract.pdf --output report.md
```

### CLI Commands

| Command | Description |
|---------|-------------|
| `summarize` | Summarize a legal document (bullet/narrative/detailed) |
| `clauses` | Extract and categorize clauses |
| `risks` | Score risk factors (0-10 per category) |
| `compare` | Compare multiple documents side by side |
| `export` | Generate comprehensive PDF-ready report |

## 🌐 Web UI (Streamlit)

```bash
streamlit run src/legal_summarizer/web_ui.py
```

The web interface provides:
- 📁 **File uploader** — Drag & drop PDF/text files
- 📋 **Summary display** — Formatted document analysis
- 📄 **Clause table** — Categorized clause extraction
- ⚠️ **Risk meter** — Visual risk assessment
- 📊 **Document comparison** — Multi-document analysis
- 📥 **Export** — Download markdown reports

## ⚙️ Configuration

Edit `config.yaml` or set environment variables:

```bash
export LEGAL_SUMMARIZER_MODEL=gemma4
export LEGAL_SUMMARIZER_TEMPERATURE=0.3
```

## 🧪 Running Tests

```bash
python -m pytest tests/ -v
```

## 📁 Project Structure

```
11-legal-doc-summarizer/
├── src/legal_summarizer/
│   ├── __init__.py          # Package init
│   ├── core.py              # Core business logic
│   ├── cli.py               # Click CLI interface
│   ├── web_ui.py            # Streamlit web interface
│   ├── config.py            # Configuration management
│   └── utils.py             # Helpers
├── tests/
│   ├── __init__.py
│   ├── test_core.py         # Core logic tests
│   └── test_cli.py          # CLI tests
├── config.yaml              # Configuration file
├── setup.py                 # Package setup
├── requirements.txt         # Dependencies
├── Makefile                 # Dev commands
├── .env.example             # Environment template
└── README.md                # This file
```

## Part of

[90 Local LLM Projects](../README.md) — A collection of projects powered by local language models.

## 📸 Screenshots

<div align="center">
<table>
<tr>
<td><img src="https://via.placeholder.com/400x250/1a1a2e/e94560?text=CLI+Interface" alt="CLI Interface"/></td>
<td><img src="https://via.placeholder.com/400x250/16213e/e94560?text=Web+UI" alt="Web UI"/></td>
</tr>
<tr>
<td align="center"><em>CLI Interface</em></td>
<td align="center"><em>Streamlit Web UI</em></td>
</tr>
</table>
</div>
