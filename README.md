# 🤖 Agentic RAG System using Python

## 📌 Project Overview

This project is a beginner-friendly implementation of an **Agentic Retrieval-Augmented Generation (RAG)** system using Python, LangChain, LangGraph, FAISS, Hugging Face embeddings, and Groq LLMs.

The system is designed to decide whether a user's question requires retrieving information from a document database or can be answered directly by a Large Language Model (LLM).

## 🎯 Project Goals

- Understand the fundamentals of Retrieval-Augmented Generation (RAG).
- Split documents into smaller chunks for efficient retrieval.
- Generate embeddings using a Hugging Face embedding model.
- Store and search document vectors using FAISS.
- Build a decision-making router to determine whether retrieval is needed.
- Use LangGraph to orchestrate the workflow.
- Generate answers using a Groq-hosted LLM.

## 🛠️ Technologies Used

- **Python** — Programming language.
- **LangChain** — Building LLM-powered applications.
- **LangGraph** — Orchestrating the agent workflow.
- **FAISS** — Vector storage and similarity search.
- **Hugging Face** — Generating text embeddings.
- **Groq** — Running the language model.
- **python-dotenv** — Managing environment variables.

## ⚙️ How It Works

The planned workflow consists of the following steps:

1. **Document Preparation:** Load the source text and convert it into document objects.
2. **Text Splitting:** Divide the text into smaller chunks using `RecursiveCharacterTextSplitter`.
3. **Embedding Generation:** Convert the chunks into numerical vectors using `sentence-transformers/all-MiniLM-L6-v2`.
4. **Vector Store Creation:** Store the vectors in FAISS.
5. **Question Routing:** Use an LLM-powered router to decide whether the question needs document retrieval.
6. **Retrieval:** Search FAISS for relevant document chunks when required.
7. **Answer Generation:** Use Groq to generate an answer using the retrieved context when available.

## 🧠 Workflow Diagram

```text
              User Question
                    |
                    v
             Question Router
                    |
          +---------+---------+
          |                   |
       Retrieve             Direct
          |                   |
          v                   |
      Search FAISS            |
          |                   |
          +---------+---------+
                    |
                    v
             Generate Answer
                    |
                    v
                   END
```

## 📂 Project Structure

```text
agentic-rag/
│
├── main.py          # Main application and workflow
├── .env             # API key configuration
├── .gitignore       # Files excluded from Git
├── requirements.txt # Python dependencies
└── README.md        # Project documentation
```

The structure can be adjusted to match the actual files in the project.

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd agentic-rag
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate it on Windows:

```powershell
.venv\Scripts\Activate.ps1
```

### 3. Install Dependencies

```bash
pip install langchain langgraph langchain-community langchain-groq langchain-huggingface sentence-transformers faiss-cpu python-dotenv
```

### 4. Configure the API Key

Create a `.env` file in the project directory:

```text
GROQ_API_KEY=your_groq_api_key
```

Replace the placeholder with your own Groq API key. Never commit your `.env` file to GitHub.

### 5. Run the Project

Once the graph and application code are complete, run:

```bash
python main.py
```

## 📚 Key Concepts Learned

- Document chunking and overlap
- Text embeddings
- Vector databases and similarity search
- Retrievers in LangChain
- LLM-based question routing
- State management with `TypedDict`
- Nodes, edges, and conditional routing in LangGraph
- Context-based answer generation

## 🚧 Current Development Status

This project is being developed step by step as a learning project.

Completed components include document chunking, embedding generation, FAISS vector store creation, retrieval configuration, and the question-routing function.

The remaining work includes completing the generation node, connecting and testing the LangGraph workflow, and validating both retrieval and direct-answer paths.

## 🔮 Future Improvements

- Support PDF and multiple document sources.
- Add answer evaluation and relevance checking.
- Improve routing reliability using structured outputs.
- Add conversation memory.
- Build a simple user interface.
- Add error handling and automated tests.

## 👨‍💻 Learning Purpose

This project is intended for educational purposes to explore how Agentic RAG systems combine retrieval, language models, and conditional workflows.

---

**Built with Python, LangChain, LangGraph, FAISS, Hugging Face, and Groq.** 🚀
