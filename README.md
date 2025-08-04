
### RAG System for LangSmith Documentation

This project is a Streamlit-based application that implements a Retrieval-Augmented Generation (RAG) pipeline to provide accurate and context-aware answers to questions based on the official LangSmith documentation. It demonstrates a full-stack approach to building an LLM-powered application, leveraging open-source and high-speed cloud services for an efficient and verifiable Q\&A experience.

-----

### Key Features

  * **Interactive Chat Interface:** A user-friendly web application built with Streamlit for submitting questions and viewing responses.
  * **Dynamic Data Ingestion:** The application scrapes and processes content from the official LangSmith documentation website (`https://docs.smith.langchain.com/`) to create a custom knowledge base.
  * **Local & Open-Source Embeddings:** Utilizes the Ollama framework with the `nomic-embed-text` model to generate text embeddings locally, ensuring data privacy and cost-free operation.
  * **High-Speed Generation:** Integrates with the Groq API to leverage the `gemma2-9b-it` model for ultra-fast, low-latency answer generation.
  * **Contextual Integrity:** The RAG pipeline ensures all answers are derived directly from the source documentation, with a "Document Similarity Search" expander to show the exact text chunks used.

-----

### Technical Stack

  * **Application Framework:** Streamlit
  * **RAG Orchestration:** LangChain
  * **Data Loading:** `WebBaseLoader`
  * **Embedding Model:** Ollama (`nomic-embed-text`)
  * **Vector Database:** FAISS
  * **LLM:** Groq API (`gemma2-9b-it`)
  * **Dependencies:** `python-dotenv`

-----

### How to Run the Project Locally

Follow these steps to set up and run the application on your local machine.

#### 1\. Prerequisites

  * Python 3.8+
  * Git
  * Ollama (installed and running)

#### 2\. Clone the Repository & Install Dependencies

Open your terminal and run the following commands:

```bash
# Clone the repository
git clone https://github.com/Aditi00073/RAG-app-for-answering-LangSmith.git

# Navigate to the project directory
cd RAG-app-for-answering-LangSmith

# Install the required Python packages
pip install -r requirements.txt
```

**Note:** You will need a `requirements.txt` file in your repository. You can generate one by running `pip freeze > requirements.txt` in your project directory. The contents should look like this:

```
streamlit
langchain
langchain-groq
langchain-community
faiss-cpu
langchain-core
ollama
python-dotenv
```

#### 3\. Set Up Ollama

Your project relies on the Ollama server to create embeddings.

  * Make sure the Ollama application is running on your computer.
  * Pull the embedding model required by the project:
    ```bash
    ollama pull nomic-embed-text
    ```

#### 4\. Configure API Keys

Create a file named `.env` in the root of your project directory and add your Groq API key:

```
GROQ_API_KEY="gsk_your_api_key_here"
```

#### 5\. Run the Streamlit Application

With all the setup complete, you can now launch the application:

```bash
streamlit run app.py
```

Your browser will open automatically, and you can start interacting with your RAG system.
