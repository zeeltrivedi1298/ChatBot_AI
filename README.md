# ChatBot_AI
# 🤖 Azure RAG Chatbot with OpenAI & Cognitive Search  

## 📌 Overview  
This project demonstrates how to build a **Retrieval-Augmented Generation (RAG) chatbot** on **Azure Cloud** using:  

This chatbot utilizes Azure OpenAI to understand complex queries and Azure Cognitive Search to retrieve data from internal knowledge bases. Such a setup ensures users receive accurate, context-rich answers in real-time, improving customer satisfaction and operational efficiency at an enterprise scale.


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

