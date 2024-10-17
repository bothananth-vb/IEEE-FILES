Retrieval-Augmented Generation (RAG) System for Question Answering

Problem Statement
This project implements a simplified Retrieval-Augmented Generation (RAG) system to answer open-domain questions. 

The system:
Retrieves relevant documents from a knowledge base based on a user's query.
Generates a natural language answer based on the retrieved content using a pre-trained language model.
Given a user query (e.g., "Who is the president of the United States?"), the system will return relevant retrieved documents and a generated answer based on those documents.

Requirements
Google Colab or a local Python environment with at least 12 GB of RAM.
Python packages:
1.datasets
2.transformers
3.torch
4.scikit-learn
5.faiss-cpu

Steps to Run
Clone this repository or download the code to your local machine or Google Colab.
Download a small dataset to use for the knowledge base. For this setup, recommend using the SQuAD dataset to prevent memory overload issues.

Approach
1. Data Preprocessing
We preprocess the SQuAD dataset, splitting it into chunks that can be used as retrieval candidates. This ensures that the retriever can fetch relevant pieces of information for the user's query.

2. Retriever Model
The system uses a TF-IDF based retrieval model to fetch the top-k relevant documents from the dataset based on the user query.

3. Generator Model
We use a pre-trained language model from Hugging Face's Transformers library (such as BART) to generate natural language answers. The model is conditioned on the retrieved documents, allowing it to produce answers that align with the retrieved content.

4. Evaluation
We use metrics such as Exact Match and F1 Score to evaluate how well the system's generated answers align with the ground truth from the SQuAD dataset.

