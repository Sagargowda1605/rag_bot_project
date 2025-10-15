Internal RAG Q&A Bot: Zero-Cost, Local Deployment

A Retrieval-Augmented Generation (RAG) system built for accurate, cost-free question answering using only internal documents (e.g., technical manuals, policy data).

This project demonstrates practical GenAI and MLOps skills — from document ingestion to local inference and Docker-ready deployment.

📄 Project Goal

To build a local, self-contained RAG pipeline capable of answering domain-specific questions without relying on paid APIs.

Key highlights:

Fully local pipeline (no API cost)

Modular architecture (data ingestion → retrieval → generation)

Lightweight deployment (CPU-friendly, Docker-ready)

🛠️ Technical Stack

| Component                        | Tool                                    | Rationale                                            |
| -------------------------------- | --------------------------------------- | ---------------------------------------------------- |
| **Framework (Orchestration)**    | LangChain                               | Seamlessly connects RAG components                   |
| **LLM Generator**                | Hugging Face Pipeline (`flan-t5-small`) | Local text generation, CPU-efficient                 |
| **Embeddings (Vector Creation)** | HuggingFaceEmbeddings                   | Local, scalable vector embedding                     |
| **Vector Store (Database)**      | ChromaDB                                | Lightweight, file-based vector storage               |
| **Deployment**                   | Docker *(planned)*                      | Simplifies production deployment and reproducibility |


Project Status
| Phase                             | Status         | Key Concepts Mastered                                                                     |
| --------------------------------- | -------------- | ----------------------------------------------------------------------------------------- |
| **I. Data Preparation & Storage** | ✅ COMPLETE     | Document loading, recursive text splitting, Hugging Face embeddings, ChromaDB persistence |
| **II. RAG Chain Setup**           | ✅ COMPLETE     | Local LLM (Flan-T5), RetrievalQA chain, MMR (Maximum Marginal Relevance) search           |
| **III. Serialization & Upgrade**  | 🔄 IN PROGRESS | Multi-format support (.pdf, .csv), model persistence (Pickle)                             |
| **IV. MLOps**                     | ⏳ TO DO        | Docker containerization for deployment                                                    |

Usage Example

from langchain.chains import RetrievalQA
# Load prebuilt chain (from pickle)
qa_chain = ...  # your loaded chain

response = qa_chain.invoke({"query": "What are the minimum system requirements for deployment?"})
print(response)
# → Factual answer based ONLY on internal documents


Next Steps

 Add FastAPI endpoint for serving responses

 Containerize with Docker for easy deployment

 Integrate logging and monitoring (basic MLOps)

📚 Concepts Demonstrated

Retrieval-Augmented Generation (RAG) architecture

Vector databases and embeddings

Local LLM usage (Hugging Face Transformers)

Document retrieval using MMR optimization

Serialization & model persistence

MLOps fundamentals with Docker