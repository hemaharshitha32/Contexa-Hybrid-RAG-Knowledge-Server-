# Contexa – Hybrid RAG Knowledge Server (MCP Protocol)

Contexa is a local Hybrid Retrieval-Augmented Generation (RAG) Knowledge Server built using the Model Context Protocol (MCP). It helps AI assistants search and retrieve information from local documents without uploading any data to the cloud.

The system combines semantic search, BM25 keyword search, and cross-encoder reranking to provide accurate and relevant search results. It works completely offline and supports multiple document formats such as PDF, Markdown, Word, PowerPoint, Excel, text files, and source code.

---

# Overview

Contexa is designed for students, developers, researchers, and organizations who need a fast and private document search system.

It automatically indexes documents stored on the local machine and allows MCP-compatible AI assistants to retrieve relevant information quickly.

---

# Features

## Hybrid Search

- Semantic vector search
- BM25 keyword search
- Hybrid retrieval
- Cross-encoder reranking
- Better search accuracy

## Document Management

- Automatic document indexing
- Incremental reindexing
- Background indexing
- Duplicate document detection
- Auto-update when files change

## Supported File Formats

- PDF
- Markdown
- Text files
- Python
- C / C++
- JavaScript
- TypeScript
- JSON
- XML
- CSV
- DOCX
- XLSX
- PPTX
- Jupyter Notebook

## Search Features

- Semantic search
- Keyword search
- Hybrid search
- Category filtering
- Similar document search
- Query expansion
- Snippet generation

## Performance

- Fast indexing
- Query caching
- Memory-efficient design
- Incremental updates
- Background processing

## Local Execution

- Works completely offline
- No cloud storage
- No API keys
- No Docker required
- Optional GPU support

---

# Technology Stack

## Backend

- Python 
- FastMCP
- ChromaDB
- ONNX Runtime
- FastEmbed

## Search Techniques

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

Combines semantic search and keyword search to provide more accurate search results.

## Local Processing

All documents remain on the local computer, ensuring privacy and security.

## Automatic Indexing

Automatically detects new or updated files and updates the search index.

## Smart Chunking

Splits large documents into smaller sections for better retrieval.

## Reranking

Ranks search results based on relevance before returning them.

## GPU Support

Supports optional NVIDIA GPU acceleration for faster processing.

---

# MCP Tools

The server provides the following MCP tools:

- search_knowledge
- get_document
- reindex_documents
- list_documents
- list_categories
- get_index_stats
- add_document
- update_document
- remove_document
- search_similar

---

# Project Structure

```text
contexa/
│
├── mcp_server/
├── documents/
├── data/
├── models_cache/
├── tests/
├── config.example.yaml
├── requirements.txt
├── README.md
└── LICENSE
```

---

# Installation

## Clone the Repository

```bash
git clone https://github.com/your-username/contexa.git

cd contexa
```

## Create a Virtual Environment

```bash
python -m venv venv
```

## Activate the Environment

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

---

# Usage

Store your documents inside the **documents/** folder.

```text
documents/
├── research/
├── notes/
├── security/
└── projects/
```

Start the MCP server:

```bash
python -m mcp_server.server
```

---

# Example Search

```python
search_knowledge(
    query="Machine Learning",
    hybrid_alpha=0.5,
    max_results=5
)
```

---

# Configuration

The project uses a **config.yaml** file to configure:

- Document directory
- Database location
- Embedding model
- Reranker model
- Chunk size
- Search settings
- GPU support

---

# Search Modes

| Mode | Description |
|------|-------------|
| Keyword Search | Searches using BM25 |
| Semantic Search | Searches using embeddings |
| Hybrid Search | Combines keyword and semantic search |
| Reranked Search | Improves result ranking |

---

# Applications

- Personal Knowledge Base
- Research Papers
- Software Documentation
- Source Code Search
- Technical Notes
- Academic Projects
- Enterprise Knowledge Management

---

# Future Improvements

- Multi-user support
- Authentication
- Web Dashboard
- REST API
- OCR Support
- Multi-language support

---



# Acknowledgments

- ChromaDB
- FastEmbed
- ONNX Runtime
- FastMCP
- PyMuPDF
- PyYAML
