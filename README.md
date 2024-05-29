# Retrieval-Augmented Generation (RAG) Framework

This repository contains the implementation of a Retrieval-Augmented Generation (RAG) framework using Large Language Models (LLMs) to answer questions based on a set of blog articles. The framework first retrieves relevant information from the provided document(articles) and generates accurate answers to the user input queries.

## Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Implementation Details](#implementation-details)
- [Dependencies](#dependencies)
- [Design Decisions](#design-decisions)
- [Challenges Faced](#challenges-faced)

## Introduction
![QNA LLM](https://github.com/tisha-prog/assign-new/assets/60807484/15448cdb-82cb-4cc6-bca5-48f32266873e)

This project has developed a RAG framework that leverages/utilizes the LLMs (OPENAI Langchain models) to generate answers to questions based on the ten blog articles. The articles have been pre-processed (data pre-processing stage) for efficient retrieval. 
The framework integrates retrieval and generation processes to provide accurate and relevant answers.

![rag_indexing-8160f90a90a33253d0154659cf7d453f](https://github.com/tisha-prog/assign-new/assets/60807484/3bc30c51-7383-4a03-aba3-36824c901883)

STEPS : 
   1. load and preprocess the raw data (articles which is document.pdf)
   2. create chunks and embeddings (OPENAIEMBEDDINGS)
   3. store in VectorDB FAISS (langchain.vectordb)
   4. then perform similarity-search query 
   5. run the query-answering process
      
## Implementation Details

The framework consists of the following components:

- Data Preparation: Load and preprocess the blog articles using PyPDFLoader.
- Embedding and Vector Store: Generate embeddings using OpenAIEmbeddings and store them in a FAISS vector store.
- Query Processing: Use a conversational retrieval chain to process queries and generate answers.

## Approach
- Retrieval-Augmented Generation (RAG): This approach combines information retrieval with language generation. It retrieves relevant sections from the provided blog articles and uses an LLM to generate comprehensive answers based on the retrieved information.
- Embedding and Vector Store: The framework uses the OpenAI embeddings to convert text into vectors and stores these vectors in a FAISS vector store for efficient similarity search.

  
## Design Decisions
- Use of OpenAI Embeddings: These embeddings were chosen for their accuracy and seamless integration with the OpenAI API, providing high-quality vector representations of the text.
- FAISS for Vector Search: FAISS was selected for its efficiency and scalability in performing similarity searches on large sets of document embeddings, making it ideal for this application.


## Challenges Faced
- Compatibility Issues: Ensuring that all dependencies, particularly faiss, work smoothly with Python 3.12.
- API Rate Limits: Managing the rate limits imposed by the OpenAI API during the embedding generation and query processing phases.
- Efficient Preprocessing: Optimizing the text preprocessing and chunking methods to ensure efficient retrieval and accuracy in response generation.

## Dependencies

- pandas
- transformers
- langchain
- faiss-cpu (or faiss-gpu if you have a GPU setup)
- openai
- pypdf
- python-dotenv
- requests

## Installation
To run this project, you need to have Python 3.12 or higher installed. Follow the steps below to set up the environment and install the required dependencies.

1. **Clone the repository:**
    ```bash
    https://github.com/tisha-prog/assign-new.git
    cd assign-new
    ```

2. **Create and activate a virtual environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3. **Install the dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4. **Create a `.env` file and add your OpenAI API key:**
    ```plaintext
    OPENAI_API_KEY=your_actual_openai_api_key_here
    ```

## Usage

1. **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```
   Open `main.ipynb` and run all cells to -

   1. load and preprocess the raw data (articles which is document.pdf)
   2. create chunks and embeddings (OPENAIEMBEDDINGS)
   3. store in vectordb FAISS (langchain.vectordb)
   4. then perform similarity-search query 
   5. run the query-answering process 

2. **Example Query:**
   Run the following code in a notebook cell to ask a question:
   ```python
   query = "What is 3D modeling?"
   docs = db.similarity_search(query)
   answer = chain.run(input_documents=docs, question=query)
   print(answer)
