# Document RAG QA Platform

A production-style Retrieval Augmented Generation (RAG) system built with:

- FastAPI
- Sentence Transformers
- Vector similarity search (scikit-learn NearestNeighbors)
- Local embedding model (all-MiniLM-L6-v2)
- Themed Light/Dark UI
- Engineering dashboard with index statistics
- Evaluation logging

---

## 🚀 Project Overview

This project implements a complete RAG pipeline:

1. Load documents from `data/docs`
2. Split into overlapping chunks
3. Generate embeddings
4. Build vector similarity index
5. Retrieve top-k chunks per query
6. Return grounded answers via REST API
7. Display results in a themed web UI

The system includes:

- `/ask` endpoint for question answering
- `/meta` endpoint for index metadata
- `/app` interactive UI (light & dark modes)
- Evaluation script with retrieval metrics

---

## 🧠 Architecture

User (Browser)
       ↓
FastAPI (/ask, /meta)
       ↓
RAG Pipeline
       ↓
Embedding Model (SentenceTransformer)
       ↓
Vector Index (NearestNeighbors)
       ↓
Document Chunks

---

## 📊 Features

- Dark / Light UI mode toggle
- Real-time question answering
- Display retrieved chunks + similarity scores
- Automatic chunk count and document count display
- JSON meta endpoint for monitoring
- Evaluation metrics (Hit Rate, MRR)
- Clean modular codebase

---

## 🛠 Installation

### 1. Create virtual environment

python -m venv .venv

Activate:

Windows:
.venv\Scripts\activate

Mac/Linux:
source .venv/bin/activate

### 2. Install dependencies

pip install -r requirements.txt

---

## ▶ Running the App

Start the API server:

uvicorn src.api:app --reload

Open browser:

http://127.0.0.1:8000/app

---

## 🔎 API Endpoints

POST /ask

Example body:

{
  "query": "What is Retrieval Augmented Generation?",
  "top_k": 3
}

GET /meta

Returns:

{
  "total_chunks": 55,
  "doc_count": 6,
  "doc_ids": [...]
}

---

## 📈 Evaluation

Run retrieval evaluation:

python -m src.eval

Logs saved in:

logs/eval_logs.json

Metrics:
- Hit Rate @ K
- Mean Reciprocal Rank (MRR)

---

## 🎯 Why This Project Matters

This is not just a demo calling an LLM API.

It demonstrates:

- Real embedding-based retrieval
- Index design decisions
- Chunking strategy
- Backend + UI integration
- Engineering observability
- Clean modular architecture

---

## 🔮 Future Improvements

- Add LLM-based answer generation (OpenAI / Claude)
- Persist vector index to disk
- Add FAISS support
- Deploy to cloud (Render, AWS, Railway)

---

## 👤 Author

Built by Mohamed Elsaka
AI Engineer | Machine Learning | GenAI Systems
