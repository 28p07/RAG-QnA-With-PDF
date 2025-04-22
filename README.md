# 📄 Conversational RAG with PDF Uploads & Chat History

This project is a **Conversational Retrieval-Augmented Generation (RAG)** system built using **LangChain**, **Groq LLM (Gemma 2B)**, **FAISS**, and **Streamlit**. It allows users to upload PDF documents, ask questions about their content, and retain context through chat history for a more interactive experience.

---

## ✨ Features

- 🔍 Chat with content from uploaded PDF files
- 🧠 Memory-aware context using chat history
- 💬 Powered by **Groq's Gemma2-9b-It** LLM for fast and accurate responses
- 🧱 Vector storage via **FAISS**
- 🔗 Uses **LangChain**’s conversational and retrieval chains
- 🌐 Intuitive **Streamlit** web interface

---

## 🧰 Tech Stack

- **LangChain**: For chaining LLM and retrieval logic
- **Groq API**: LLM backend (Gemma 2B)
- **FAISS**: Vector similarity search for document retrieval
- **Streamlit**: Web application UI
- **HuggingFace Embeddings**: `all-MiniLM-L6-v2` for encoding text
- **PyPDFLoader**: For loading and parsing PDF content
- **dotenv**: To manage environment variables

---

## 📂 Project Structure

```
.
├── app.py                 # Streamlit application with RAG logic
├── requirements.txt       # Python dependencies
├── .env                   # Contains HF_TOKEN (not shared)
├── temp.pdf               # Temporary file for PDF uploads
```

---

## 🚀 Getting Started

### 📦 Prerequisites

- Python ≥ 3.8
- Groq API Key
- HuggingFace Token

### 🔧 Installation

1. **Clone the repository**
```bash
git clone https://github.com/28p07/RAG-QnA-With-PDF.git
cd RAG-QnA-With-PDF
```

2. **Create `.env` file**
```env
HF_TOKEN=your_huggingface_token
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Run the app**
```bash
streamlit run app.py
```

---

## 🔑 How to Use

1. Enter your **Groq API Key** when prompted.
2. Upload one or multiple PDF files.
3. Enter a **Session ID** (used to store chat history).
4. Ask questions based on your uploaded PDFs.
5. The assistant will respond using the content of the documents and retain the conversation context.

---

## 🧠 Core Logic

### 1. **Document Loading & Splitting**
- PDFs are loaded using `PyPDFLoader`.
- Text is split using `RecursiveCharacterTextSplitter`.

### 2. **Vectorization**
- Documents are embedded using HuggingFace's `all-MiniLM-L6-v2`.
- FAISS is used to store and retrieve similar chunks.

### 3. **Conversational RAG**
- **create_history_aware_retriever**: Reformulates questions with context.
- **create_stuff_documents_chain**: Answers using relevant chunks.
- **RunnableWithMessageHistory**: Maintains session-specific conversation history.

---

## 📌 Example Use Case

- Upload mental health research PDFs.
- Ask questions like:  
  > "What are common symptoms of anxiety?"  
  > "What treatments were recommended?"  
- Get answers grounded in the content you uploaded with continuity in follow-up questions.

---

## ⚠️ Notes

- Only supports `.pdf` files for now.
- Make sure your Groq API key is valid.
- HuggingFace embedding model requires `HF_TOKEN`.


---

## 🙋‍♂️ Acknowledgements

- [LangChain](https://github.com/langchain-ai/langchain)
- [Groq](https://groq.com)
- [Hugging Face](https://huggingface.co)
- [Streamlit](https://streamlit.io)

---