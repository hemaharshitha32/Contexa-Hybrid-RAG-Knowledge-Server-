# Contexa – Hybrid RAG Knowledge Server (MCP Protocol)

Contexa is a fully local Retrieval-Augmented Generation (RAG) knowledge server built on the Model Context Protocol (MCP). It enables AI assistants to search local documents without sending data to the cloud. The system indexes PDFs, Markdown files, source code, Office documents, notebooks, and many other file formats using hybrid search techniques that combine semantic search, BM25 keyword search, and cross-encoder reranking.

The entire system runs on your machine using ONNX Runtime, requiring no external APIs, Docker, Ollama, or cloud services.

---

## Overview

Contexa provides an intelligent document retrieval system designed for developers, researchers, students, and organizations that require private, fast, and accurate document search.

The system automatically indexes local documents and exposes them through the Model Context Protocol (MCP), allowing AI assistants such as Claude Desktop and other MCP-compatible clients to retrieve relevant information efficiently.

---

## Features

### Hybrid Search

- Semantic vector search
- BM25 keyword search
- Reciprocal Rank Fusion (RRF)
- Cross-Encoder reranking
- Adjustable hybrid search ratio

### Document Management

- Automatic document indexing
- Incremental reindexing
- Background indexing
- Duplicate detection
- File watcher with automatic updates
- CRUD operations for documents

### Supported File Formats

- Markdown (.md)
- Text (.txt)
- PDF (.pdf)
- Python (.py)
- C / C++
- JavaScript
- TypeScript
- JSX / TSX
- JSON
- XML
- CSV
- DOCX
- XLSX
- PPTX
- Jupyter Notebook (.ipynb)

### AI Search Capabilities

- Semantic similarity search
- Keyword search
- Hybrid search
- Category filtering
- Query expansion
- Snippet generation
- Similar document search
- Retrieval evaluation

### Performance

- Fast BM25 inverted index
- Query caching
- Lazy model loading
- Incremental indexing
- Background reindexing
- Memory-efficient architecture

### Local Execution

- Runs completely offline
- No API keys required
- No cloud storage
- No Docker required
- ONNX Runtime inference
- Optional NVIDIA GPU acceleration

---

# Technology Stack

## Backend

- Python 3.11+
- FastEmbed
- ONNX Runtime
- ChromaDB
- FastMCP

## Search

- Semantic Embeddings
- BM25
- Reciprocal Rank Fusion (RRF)
- Cross-Encoder Reranking

## Storage

- ChromaDB
- Local File System
- YAML Configuration

## AI Models

- BAAI/bge-small-en-v1.5
- Xenova/ms-marco-MiniLM-L-6-v2

---

# Key Capabilities

## Hybrid Retrieval

Combines semantic embeddings with BM25 keyword search to provide highly accurate document retrieval.

## Local AI

Processes and searches documents entirely on the local machine without uploading data to external services.

## Automatic Indexing

Detects newly added or modified documents and updates the knowledge base automatically.

## Smart Chunking

Uses markdown-aware chunking for documentation and language-aware parsing for source code files.

## Cross-Encoder Reranking

Improves retrieval quality by reranking search results based on contextual relevance.

## GPU Support

Supports optional CUDA acceleration for faster indexing and query processing.

## Incremental Updates

Only modified documents are reindexed, significantly reducing indexing time.

---

# MCP Tools

Contexa provides the following MCP tools:

- search_knowledge
- get_document
- reindex_documents
- get_reindex_status
- list_documents
- list_categories
- get_index_stats
- add_document
- update_document
- remove_document
- add_from_url
- search_similar
- evaluate_retrieval

---

# Project Structure

```text
contexa/
│
├── mcp_server/
│   ├── config.py
│   ├── ingestion.py
│   ├── server.py
│   └── __init__.py
│
├── documents/
│
├── data/
│   ├── chroma_db/
│   └── index_metadata.json
│
├── models_cache/
│
├── presets/
│
├── tests/
│
├── config.example.yaml
├── requirements.txt
├── pyproject.toml
├── install.sh
├── install.ps1
├── LICENSE
└── README.md
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/your-username/contexa.git

cd contexa
```

## Create Virtual Environment

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### Linux/macOS

```bash
source venv/bin/activate
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Initialize

```bash
contexa init
```

---

# Usage

Place your documents inside the `documents/` directory.

```text
documents/
├── research/
├── security/
├── development/
├── notes/
└── general/
```

Start the MCP server:

```bash
python -m mcp_server.server
```

---

# Example Search

```python
search_knowledge(
    query="SQL injection",
    hybrid_alpha=0.5,
    max_results=5
)
```

---

# Configuration

The application is configured using a `config.yaml` file.

Configuration options include:

- Documents directory
- Data directory
- Model cache
- Chunk size
- Chunk overlap
- Embedding model
- Reranker model
- Search settings
- Category mappings
- Query expansion
- GPU acceleration
- Server transport

---

# Supported Search Modes

| Mode | Description |
|------|-------------|
| Keyword Search | BM25 only |
| Semantic Search | Embedding similarity |
| Hybrid Search | BM25 + Semantic |
| Reranked Search | Hybrid + Cross Encoder |

---

# Use Cases

- Personal Knowledge Base
- Software Documentation
- Research Papers
- Company Documentation
- Source Code Search
- Technical Notes
- Security Documentation
- Academic Projects
- Offline AI Search
- Enterprise Knowledge Management

---

# Future Enhancements

- Distributed indexing
- Multi-user support
- Authentication
- Web dashboard
- REST API
- Graph-based retrieval
- OCR support
- Image embeddings
- Multi-language retrieval
- Knowledge graph integration

---

# Contributing

Contributions are welcome.

1. Fork the repository.

2. Create a feature branch.

```bash
git checkout -b feature/new-feature
```

3. Commit your changes.

```bash
git commit -m "Add new feature"
```

4. Push your branch.

```bash
git push origin feature/new-feature
```

5. Open a Pull Request.

---

# License

This project is licensed under the MIT License.

See the `LICENSE` file for more information.

---

# Acknowledgments

- ChromaDB
- FastEmbed
- ONNX Runtime
- FastMCP
- PyMuPDF
- PyYAML
- Beautiful Soup
- python-docx
- openpyxl
- python-pptx
