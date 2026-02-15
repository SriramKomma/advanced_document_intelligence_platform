LLM-Powered Document Intelligence Platform
Introduction

QueryPilot is a Retrieval-Augmented Generation (RAG) based document intelligence system that allows users to upload documents and query them using natural language.

The system processes documents, generates embeddings, stores them in a vector database, retrieves relevant information, and uses a Large Language Model (LLM) to generate accurate, context-aware responses.

System Architecture

The platform is built using a modular 5-layer architecture:

User Layer (Streamlit UI)

API Layer (FastAPI)

RAG System Core

Data Storage Layer

External Systems

1️⃣ User Layer (Streamlit UI)

The User Layer provides the interface for interacting with the system.

Responsibilities:

Upload documents (PDF, DOCX, TXT, Images)

Ask questions in natural language

View AI-generated responses

Display document references and images

Manage workspaces

Streamlit acts as the frontend interface and communicates with the FastAPI backend.

2️⃣ API Layer (FastAPI)

The API Layer acts as the communication bridge between the frontend and the RAG core.

Responsibilities:

Handle file uploads

Handle user queries

Route requests to the RAG engine

Return responses to frontend

Manage workspaces and files

Example endpoints:

POST /upload
POST /query
GET /workspaces


FastAPI ensures scalability, asynchronous handling, and production readiness.

3️⃣ RAG System Core

The RAG (Retrieval-Augmented Generation) Core is the brain of the system.

It consists of:

Document Processor

Embedding Generator

Vector Search Engine

Language Model

Retrieval Logic

Document Processing Pipeline

Extract text from document

Clean and normalize content

Split into chunks

Generate embeddings

Store embeddings in vector database

Query Processing Flow

Receive user question

Convert question into embedding

Retrieve top-k similar document chunks

Construct prompt with retrieved context

Send prompt to LLM

Generate grounded answer

Return response to user

This architecture reduces hallucinations and ensures responses are based on document context.

4️⃣ Data Storage Layer

The system uses two storage mechanisms:

1. Vector Database (ChromaDB / FAISS)

Stores:

Text embeddings

Image embeddings

Metadata

Document IDs

Used for semantic similarity search.

2. Relational Database (MySQL)

Stores:

Workspace information

File metadata

User credentials

Upload records

3. File Storage

Stores:

Original uploaded documents

Processed assets

5️⃣ External Systems

The architecture allows integration with external systems such as:

Google Gemini API (LLM provider)

Cloud storage systems

Enterprise document repositories

Third-party APIs

Authentication services

This ensures the platform is extensible and production-ready.

Technology Stack
Frontend

Streamlit

Backend

FastAPI

Python 3.11

AI & Embeddings

Sentence Transformers

Google Gemini API (LLM)

Databases

MySQL

ChromaDB

Infrastructure

Docker

Nginx

Deployment
Development
docker-compose up -d


Access:

http://localhost:8501

Why This Architecture?

Modular and scalable

Clear separation of concerns

LLM grounded with document context

Supports multi-modal data

Production deployable

Easily extendable
