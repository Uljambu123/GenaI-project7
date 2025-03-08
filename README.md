# Conversational RAG with PDF Uploads and Chat History

## 1. Project Overview

This project implements a Conversational Retrieval-Augmented Generation (RAG) system using Streamlit. Users can upload PDF files, and the system allows interactive question-answering based on the document's content. The chat history is maintained for better contextual responses.

## 2. Objective

The goal of this project is to build an interactive AI assistant that can:
- Accept and process PDF uploads.
- Retrieve relevant information from the documents.
- Maintain conversational context and provide meaningful responses.
- Use embedding-based search for efficient document retrieval.

## 3. Key Steps in the Project

1. **Setting up Streamlit UI**:
   - Create an interactive web application using Streamlit.
   - Provide an interface for users to upload PDFs and enter queries.

2. **Processing Uploaded PDFs**:
   - Load and parse PDFs using `PyPDFLoader`.
   - Split text into manageable chunks using `RecursiveCharacterTextSplitter`.

3. **Embedding and Retrieval**:
   - Generate document embeddings using `HuggingFaceEmbeddings`.
   - Store and retrieve documents using `Chroma` vector database.

4. **Contextualized Question Reformulation**:
   - Implement a history-aware retriever using `create_history_aware_retriever`.
   - Reformulate user queries by considering past interactions.

5. **Answer Generation**:
   - Utilize a language model (`ChatGroq` with `Gemma2-9b-It`) to generate responses.
   - Ensure responses are concise and context-aware.

6. **Managing Chat History**:
   - Maintain chat history across user sessions using `ChatMessageHistory`.
   - Use `RunnableWithMessageHistory` to integrate retrieval and generation with chat history.

7. **Interactive Q&A**:
   - Accept user queries through the UI.
   - Retrieve relevant document snippets and provide concise, accurate answers.

## 4. Conclusions

- The project successfully integrates Conversational RAG with document-based Q&A.
- Users can interactively query documents, and responses improve with chat history.
- Using embeddings and vector storage enhances retrieval accuracy.
- The approach is scalable and can be extended to handle multiple document formats.

## 5. Technologies Used

- **Programming Language**: Python
- **Framework**: Streamlit
- **Libraries**:
  - `langchain` (for RAG-based retrieval and chat history management)
  - `PyPDFLoader` (for PDF processing)
  - `HuggingFaceEmbeddings` (for text embeddings)
  - `Chroma` (for vector storage)
  - `ChatGroq` (for LLM-based response generation)
  - `dotenv` (for API key management)
  - `os` (for file handling)

## 6. Future Work

- Support additional document formats (e.g., Word, TXT).
- Improve query understanding using more advanced LLMs.
- Optimize retrieval and response speed.
- Implement multi-document search across uploaded files.
- Enhance UI with better visualization and conversation memory.

## 7. How to Run

### Prerequisites
- Install dependencies:

  pip install streamlit langchain langchain_chroma langchain_community langchain_core langchain_groq langchain_huggingface langchain_text_splitters python-dotenv

- Set up environment variables:
echo "HF_TOKEN=your_huggingface_api_key" > .env

## Running the Application
Start the Streamlit app:
- streamlit run Conversational_RAG.py

- Enter the Groq API Key in the input box.
- Upload a PDF file.
- Enter your query in the chat input field.
The assistant will respond with relevant information extracted from the document.
