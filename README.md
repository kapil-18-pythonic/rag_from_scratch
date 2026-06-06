# RAG From Scratch

A modular Retrieval-Augmented Generation (RAG) system built from scratch using FAISS, Sentence Transformers, and Hugging Face models.

## Overview

This project implements a complete RAG pipeline from scratch instead of relying on high-level frameworks. The goal is to understand and build every major component involved in modern retrieval systems.

## Features

* Multi-PDF ingestion
* Parent-Child chunking strategy
* Dense retrieval using Sentence Transformers
* FAISS vector database

  * Flat Index
  * IVF Index
  * HNSW Index
* Parent document expansion
* Cross-Encoder reranking
* Context construction
* LLM-based answer generation
* Persistence support
* Modular architecture

## Architecture

```text
PDF Documents
      │
      ▼
Document Loader
      │
      ▼
Parent-Child Chunker
      │
      ▼
Embedding Model
      │
      ▼
FAISS Vector Store
      │
      ▼
Retriever
      │
      ▼
Cross-Encoder Reranker
      │
      ▼
Context Builder
      │
      ▼
LLM Generator
      │
      ▼
Answer
```

## Project Structure

```text
rag_from_scratch/
│
├── configs/
│   └── config.py
│
├── experiments/
│
├── models/
│   └── model.py
│
├── rag/
│   ├── loader.py
│   ├── chunker.py
│   ├── embedder.py
│   ├── vectorstore.py
│   ├── retriever.py
│   ├── reranker.py
│   ├── context_builder.py
│   ├── generator.py
│   ├── ingestion.py
│   └── pipeline.py
│
├── main.py
├── requirements.txt
└── README.md
```

## Retrieval Pipeline

1. Load one or more PDF documents
2. Split documents into parent chunks
3. Split parent chunks into child chunks
4. Generate embeddings for child chunks
5. Store embeddings in FAISS
6. Retrieve top-k child chunks
7. Expand retrieved results to parent chunks
8. Rerank retrieved documents
9. Build context
10. Generate final answer

## Tech Stack

* Python
* FAISS
* Sentence Transformers
* Hugging Face Transformers
* PyPDF
* LangChain Text Splitters

## Future Improvements

* Hybrid Search (BM25 + Dense Retrieval)
* Query Expansion
* Evaluation Framework
* Agentic RAG
* Distillation Experiments
* Vision RAG
* Audio RAG

## Motivation

The objective of this project is to gain a deep understanding of retrieval systems by implementing the core components manually rather than relying entirely on frameworks.
