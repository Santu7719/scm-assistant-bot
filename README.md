# scm-assistant-bot


## Overview
SCM Assistant is a Retrieval-Augmented Generation (RAG) chatbot built using Flowise, Google Gemini, and Qdrant. It answers questions related to supplier performance and supply chain governance policies by combining structured supplier data with governance documents.

## Architecture
- LLM: Google Gemini
- Embeddings: Gemini Embedding (gemini-embedding-001)
- Vector Database: Qdrant Cloud
- Framework: Flowise
- Retrieval Strategy: Conversational Retrieval QA Chain

## Knowledge Sources
### Supplier Performance Data
- Source: supplier_performance_data.csv
- Split into: 20 CSV files of 100 records each
- Total CSV Chunks: 2000

### Governance Policy
- Source: SupplyChain_Governance_Policy_v3.2.pdf
- PDF Chunks: 35

Total indexed vectors: 2035

## Chunking Strategy
### CSV
- Splitter: Recursive Character Text Splitter
- Chunk Size: 2000
- Chunk Overlap: 0

### PDF
- Usage: One document per page
- Splitter: Recursive Character Text Splitter
- Chunk Size: 500
- Chunk Overlap: 50

## Challenges Faced
- Gemini embedding quota limitations
- Qdrant vector dimension mismatch
- Voyage AI integration errors in Flowise
- Flowise document store upsert issues

## Solutions
- Split large CSV into smaller files
- Used Qdrant Cloud for persistent vector storage
- Reconfigured embeddings using Gemini
- Sequential ingestion with smaller batches

## Public Chatbot Link
[Add Link]

## Chatflow Export
scm_assistant.json
