# AI Assistant RAG PDF Telegram Workflow

This n8n workflow template creates a personal AI assistant on Telegram that can answer questions about PDF documents you upload.

## Features

- **Telegram Integration**: Interacts with users through a Telegram bot.
- **PDF Processing**: Extracts text from PDF documents.
- **Vector Store Integration**: Uses Pinecone to store and retrieve document embeddings.
- **RAG Implementation**: Implements a Retrieval-Augmented Generation (RAG) pipeline to answer questions based on the content of the uploaded PDFs.
- **Powered by OpenAI and Groq**: Uses OpenAI for embeddings and Groq for the language model.

## Setup

1.  **Import `ai_assistant_rag_pdf_telegram.json` into n8n.**
2.  **Add your credentials** for:
    - OpenAI
    - Telegram
    - Pinecone
    - Groq
3.  **Update placeholder values** in the nodes (e.g., Pinecone index name).
4.  **Activate the workflow.**
