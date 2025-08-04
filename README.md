### **Project Title:** RAG System for PyTorch Documentation using Groq and Ollama

### **Overview**
This project is a Streamlit-based application that implements a Retrieval-Augmented Generation (RAG) pipeline to provide accurate and context-aware answers to questions about PyTorch's official documentation. By integrating a local embedding model with a high-speed LLM, the system offers an efficient and verifiable way to query a custom knowledge base.

### **Key Features**
* **Interactive Chat Interface:** A user-friendly web interface built with Streamlit for submitting questions and viewing responses.
* **Dynamic Data Ingestion:** Automatically scrapes and processes content from a live website (PyTorch's documentation) to create an up-to-date knowledge base.
* **Local & Open-Source Embeddings:** Utilizes the Ollama framework with the `nomic-embed-text` model to generate text embeddings locally, ensuring data privacy and cost-free operation.
* **High-Speed Generation:** Integrates with the Groq API to leverage the `gemma2-9b-it` model for ultra-fast, low-latency answer generation.
* **Contextual Integrity:** The RAG pipeline ensures that all answers are directly derived from the source documentation, with a "Document Similarity Search" expander to show the exact text chunks used to formulate the response.

### **Technical Stack**
* **Application Framework:** Streamlit
* **RAG Orchestration:** LangChain
* **Data Loading:** `WebBaseLoader`
* **Embedding Model:** Ollama with `nomic-embed-text`
* **Vector Database:** FAISS
* **LLM:** Groq API with `gemma2-9b-it`
* **Dependencies:** `python-dotenv` for managing API keys.

### **How It Works**
1.  **Data Ingestion:** The application first loads content from the PyTorch documentation website, splits the text into manageable chunks, and converts each chunk into a numerical vector using the **Ollama embedding model**.
2.  **Vector Store Creation:** These vectors are stored in an in-memory **FAISS vector database**, creating a searchable index of the documentation.
3.  **Retrieval:** When a user asks a question, the system uses the same Ollama embedding model to convert the question into a vector. It then performs a similarity search in the FAISS database to retrieve the most relevant text chunks from the documentation.
4.  **Augmented Generation:** The user's question, along with the retrieved text chunks, is sent to the **Groq LLM (`gemma2-9b-it`)**.
5.  **Final Output:** The LLM generates a concise and accurate answer based **only** on the provided context, which is then displayed to the user in the Streamlit interface.
