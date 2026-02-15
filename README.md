📄 AI Document Intelligence Platform 

An end-to-end LLM-powered Document Intelligence System built using:

⚛️ React (Frontend UI)

🧠 PaddleOCR (OCR Engine)

📑 PyMuPDF (PDF Parsing)

🔎 all-MiniLM-L6-v2 (Embeddings)

🗂 FAISS (Vector Database)

🚀 Groq API (LLM Inference)

This system extracts, indexes, and intelligently answers questions from uploaded documents using Retrieval-Augmented Generation (RAG).

🖥️ Application Screenshot

🏗️ Architecture Overview
User (React UI)
        ↓
OCR (PaddleOCR)
        ↓
PDF Parsing (PyMuPDF)
        ↓
Text Chunking
        ↓
Embeddings (all-MiniLM-L6-v2)
        ↓
FAISS Vector Store
        ↓
Groq API (LLM)
        ↓
Response to User

📦 Tech Stack
🎨 User Layer (Frontend)

React.js

Axios (API calls)

Modern UI with document upload & chat interface

🔍 Document Processing Layer

PaddleOCR → Extract text from images & scanned PDFs

PyMuPDF → Parse structured PDF content

Custom Text Chunking → Split text for embedding

🧠 Embedding Model

all-MiniLM-L6-v2

Converts text chunks into dense vectors

🗄 Vector Database

FAISS

Fast similarity search

Stores document embeddings

🚀 API Layer

FastAPI (Backend)

Groq API (LLM inference)

RAG Pipeline integration

⚙️ Features

✅ Upload PDF / Image documents

✅ OCR for scanned documents

✅ Automatic text extraction

✅ Semantic search using FAISS

✅ Groq-powered LLM responses

✅ Context-aware Q&A (RAG)

✅ Clean React UI

📂 Project Structure
project-root/
│
├── frontend/              # React Application
│
├── backend/
│   ├── main.py            # FastAPI server
│   ├── ocr.py             # PaddleOCR logic
│   ├── pdf_parser.py      # PyMuPDF logic
│   ├── embeddings.py      # MiniLM embedding logic
│   ├── vector_store.py    # FAISS setup
│   ├── rag_pipeline.py    # Retrieval + Groq integration
│
├── docs/
│   └── screenshot.jpg
│
├── requirements.txt
└── README.md

🔄 RAG Pipeline Flow
1️⃣ Upload Document

User uploads PDF/Image via React UI.

2️⃣ OCR Processing

PaddleOCR extracts text (for scanned docs).

3️⃣ PDF Parsing

PyMuPDF extracts structured text & metadata.

4️⃣ Text Chunking

Large text is split into manageable chunks.

5️⃣ Embedding Generation

all-MiniLM-L6-v2 converts chunks into vectors.

6️⃣ FAISS Indexing

Vectors stored in FAISS for similarity search.

7️⃣ Query Processing

User question →

Convert question into embedding

Retrieve top relevant chunks from FAISS

Send context + question to Groq API

8️⃣ Final Answer

LLM generates accurate context-grounded response.

🔐 Environment Variables

Create a .env file in backend:

GROQ_API_KEY=your_groq_api_key

🛠️ Installation Guide
1️⃣ Clone Repository
git clone https://github.com/your-username/your-repo.git
cd your-repo

2️⃣ Backend Setup
cd backend
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows

pip install -r requirements.txt


Run backend:

uvicorn main:app --reload

3️⃣ Frontend Setup
cd frontend
npm install
npm start

📡 API Endpoints
Method	Endpoint	Description
POST	/upload	Upload document
POST	/query	Ask question
GET	/health	API status
🧠 Why Groq API?

⚡ Ultra-fast inference

💰 Free-tier friendly

🧠 Supports LLaMA models

🚀 Great for RAG systems

📊 Future Improvements

Multi-document support

Persistent vector storage

User authentication

Conversation memory

Streaming responses

Cloud deployment (AWS/GCP)

👨‍💻 Author

Built as a full-stack AI Document Intelligence System using modern RAG architecture.
