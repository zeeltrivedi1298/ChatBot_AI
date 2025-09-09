

# 🤖 Create Chatbot using Azure AI Search & Azure OpenAI with Own Data

This project demonstrates how to build a **Retrieval-Augmented Generation (RAG) chatbot** on **Azure Cloud** using:  


This chatbot utilizes Azure OpenAI to understand complex queries and Azure Cognitive Search to retrieve data from internal knowledge bases. Such a setup ensures users receive accurate, context-rich answers in real-time, improving customer satisfaction and operational efficiency at an enterprise scale.


## 📌 Overview
This project demonstrates how to build a **Retrieval-Augmented Generation (RAG) chatbot** on **Azure Cloud** by integrating:

- **Azure OpenAI** → for natural language understanding (GPT models, embeddings)
- **Azure Cognitive Search (AI Search)** → for semantic + vector retrieval
- **Azure Blob Storage** → for storing proprietary data

This setup allows organizations to deliver **context-rich, accurate, and real-time answers** from their internal knowledge base, improving customer satisfaction and employee productivity:contentReference[oaicite:0]{index=0}.

---

## ⚙️ Architecture
1. **Upload Data** → Store files (PDF, TXT, JSON, CSV) in Azure Blob Storage.
2. **Indexing** → Import and index data into Azure Cognitive Search.
3. **Embedding** → Use OpenAI `text-embedding-3-large` for semantic search.
4. **Retrieval** → Query Cognitive Search to fetch the most relevant documents.
5. **Generation** → GPT model (`gpt-35-turbo` or higher) produces grounded responses.

---

## 🚀 Setup Guide

### 1. Prerequisites
- Azure Subscription with access to **Azure OpenAI Service**.
- Azure Cognitive Search resource.
- Azure Storage Account & Container with your documents uploaded:contentReference[oaicite:1]{index=1}.

### 2. Create Azure Resources
- **Azure Search Service**  
  Configure name, region, pricing tier, and link to storage.
- **Azure Storage Account**  
  Create blob container and upload data.
- **Azure OpenAI Resource**  
  Deploy GPT model (`gpt-35-turbo`) and embedding model (`text-embedding-3-large`):contentReference[oaicite:2]{index=2}.

### 3. Configure Data Connection
- Import Blob Storage data into **Azure Cognitive Search**.
- Configure index fields (e.g., `content`, `title`, `fileName`, `url`).
- Choose **Semantic Search** for contextual results:contentReference[oaicite:3]{index=3}.

### 4. Deploy & Test
- Go to **Azure OpenAI Studio → Playground**.
- Connect your AI Search index to the GPT model.
- Query with natural language:
  - ✅ If data exists → returns contextual answer with references.
  - ⚠️ If not → responds with fallback (e.g., *“Data does not exist in provided source”*):contentReference[oaicite:4]{index=4}.

---

## 📜 Example Queries

### When Data Exists
```text
Q: What are the total votes in all states?
A: Delaware: 504,010  
   Florida: 11,067,456  
   Georgia: 4,997,716  
   ...



- **Azure OpenAI Service** → embeddings (`text-embedding-3-large`) + chat model (`gpt-35-turbo`)  
- **Azure Cognitive Search** → vector + semantic retrieval  
- **Azure Blob Storage** → document storage  

The chatbot retrieves relevant documents from Azure Blob, indexes them in Cognitive Search, and uses Azure OpenAI to generate **context-aware responses**.  

---

## ⚙️ Architecture  

1. **Data Upload** → Store documents (PDF, TXT, CSV, JSON) in **Azure Blob Storage**.  
2. **Indexing** → Azure Cognitive Search parses documents and builds a vector index.  
3. **Embedding** → Text embeddings created using `text-embedding-3-large`.  
4. **Retrieval** → Search API returns top-matching documents.  
5. **Generation** → GPT model (`gpt-35-turbo`) produces final answers grounded in retrieved data.  

---

