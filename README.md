# LangChain RAG NLP – Project README
## 📌 Overview

This project demonstrates Retrieval-Augmented Generation (RAG) using LangChain, ChromaDB, and an open‑source LLM (Qwen2.5‑7B‑Instruct). It loads PDF course materials, splits them into chunks, generates embeddings, stores them in a vector database, and answers user questions strictly based on the PDF content.

## 🚀 Features

Load multiple PDF documents

Smart chunking using RecursiveCharacterTextSplitter

Vector embeddings with SentenceTransformers

Vector storage using ChromaDB

Retrieval using similarity search

RAG chain based on LangChain

LLM inference using Qwen2.5‑7B‑Instruct

Works in Kaggle Notebook with GPU P100

## 📁 Project Structure
```bash
project/
│-- tp-rag-langchain-nlp.ipynb
│-- README.md
```
## 📄 Requirements

Install dependencies:
```bash
!pip install -U langchain langchain-community langchain-core \
  langchain-text-splitters chromadb \
  sentence-transformers transformers
```
## 🔧 How It Works
### 1. Load PDFs

Using PyPDFLoader, the project loads and extracts pages as LangChain Documents.

### 2. Chunking

Documents are split into overlapping chunks:

chunk_size = 800

chunk_overlap = 200

### 3. Embeddings

SentenceTransformers model:

sentence-transformers/all-MiniLM-L6-v2
### 4. Vector Store

ChromaDB creates a persistent vectorstore using embeddings.

### 5. RAG Chain

The retrieval + LLM pipeline:

Retrieve top-k relevant chunks

Format them into a strict RAG prompt

Generate answer using Qwen2.5‑7B‑Instruct

## ▶️ Usage

Run the notebook, then ask questions interactively:

>>> Question : Qu'est-ce que le NLP ?
>>> Question : Explain transformers architecture.
>>> Question : exit
## 📌 RAG Rules (Strict)

The model must:

Answer only using the PDF context

Answer in the same language as the question

Say "I don't know" when the answer is not in the PDFs

## 🔮 Future Improvements

Add hybrid or MMR retrieval

Add metadata-based filtering

Try with larger embedding models

Evaluate RAG performance (precision & recall)

## 🧑‍💻 Author

SARA – Master student in AI & Emerging Technologies

Project developed as part of NLP LLM/RAG coursework.

## ⭐ Support

If you use this repo, don't forget to star ❤️ it on GitHub!
