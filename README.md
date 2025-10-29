# AI-Document_QA
Chat with PDF is a Retrieval-Augmented Generation (RAG) application built with Streamlit, Google Gemini, FAISS, and SentenceTransformers. It allows users to upload any PDF and ask natural-language questions about its content, with all context retrieved locally for privacy.

## Overview
Chat with PDF uses a combination of local embeddings and Google Gemini to deliver accurate, grounded answers to questions about any document you upload.

## Features
- Upload any PDF and index its content in seconds
-  Local embeddings with all-MiniLM-L6-v2 (SentenceTransformers) — no cost, no privacy issues
-  FAISS vector search for efficient semantic retrieval
-  Gemini LLM integration (1.5 Flash / Pro) for context-aware Q&A
-  Streamlit interface for easy interaction
-  Secure & Private: all document text and embeddings stay local
-  Free-tier friendly — runs entirely on free Google API usage
-  Tech Stack
-  
## Component	Tool
Frontend/UI	-> Streamlit
Text Extraction	-> PyMuPDF (fitz)
Embeddings ->	SentenceTransformers (all-MiniLM-L6-v2)
Vector Store ->	FAISS
LLM	-> Google Gemini (1.5 Flash / Pro)
Language ->	Python 3.10+

## Project Architecture
PDF → PyMuPDF → Chunk Text → SentenceTransformers → FAISS → Gemini → Streamlit UI

This is a RAG (Retrieval-Augmented Generation) pipeline:
Extracts text from your uploaded PDF.
Splits text into small overlapping chunks.
Converts chunks to embeddings (semantic vectors).
Stores them in FAISS for efficient similarity search.
On every query, retrieves the most relevant chunks.
Sends retrieved context + question to Gemini for an accurate, grounded answer.


