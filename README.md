# Retrieval-Augmented Generation (RAG) Framework

This repository contains the implementation of a Retrieval-Augmented Generation (RAG) framework using Large Language Models (LLMs) to answer questions based on a set of blog articles. The framework first retrieves relevant information from the provided document(articles) and generates accurate answers to the user input queries.

## Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Implementation Details](#implementation-details)
- [Dependencies](#dependencies)
- [Approach and Design Decisions](#approach-and-design-decisions)
- [Challenges Faced](#challenges-faced)
- [Technical Skills](#technical-skills)

## Introduction
This project has developed a RAG framework that leverages/utilizes current LLMs to generate answers to questions based on the ten blog articles. The articles have been pre-processed for efficient retrieval (data pre-processing stage). 
The framework integrates retrieval and generation processes to provide accurate and relevant answers.

## Installation
To run this project, you need to have Python 3.12 or higher installed. Follow the steps below to set up the environment and install the required dependencies.

1. **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/rag-framework.git
    cd rag-framework
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
1. **Download the blog articles from the provided links and place them in the `articles` directory.**

2. **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```
   Open `rag_framework.ipynb` and follow the steps to load and preprocess the articles, create embeddings, and run the query-answering process.

3. **Example Query:**
   Run the following code in a notebook cell to ask a question:
   ```python
   query = "What is 3D modeling?"
   docs = db.similarity_search(query)
   answer = chain.run(input_documents=docs, question=query)
   print(answer)
