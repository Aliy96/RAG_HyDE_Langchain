# RAG_HyDE_Langchain
A Hypothetical Document Embedding (HyDE) assisted RAG pipeline with Langchain

## Introduction
The goal of this project is to develop a medical question-answering system that provides responses to users based on collected information and a large language model (LLM). By utilizing retrieved information as context in the model's prompt, the system enhances the accuracy of responses within the medical domain and minimizes hallucinations in the model's answers.

## Data Collection
The information used in this system includes Wikipedia pages on **548 diseases**, which were collected using the Wikipedia API. The collected data was divided into **5695 sections**, totaling **665,000 tokens**. Each section contains part of the explanation for a disease, and the sectioning process was carefully designed to ensure proper embedding and retrieval functionality.

## Model & Embedding
The system utilizes the **Expanse AYA** model, which is a **fine-tuned version of LLaMA-8B**. This model was chosen for its efficient performance in Persian language processing and its relatively small size.

For **embedding the information**, we used **Farsi Parsebert Transformer Sentence 2.0**, and the embeddings are stored using **FAISS**. To retrieve relevant sections, **Cosine Similarity** is employed, ensuring effective matching of query inputs with stored medical knowledge.

## Pipeline

![Pipeline](RAG-Pipeline.jpg?raw=true "Pipeline")

1. The user inputs a medical-related query.
2. The LLM generates a **hypothetical answer** based on the query (HyDE approach).
3. The system retrieves the most relevant information based on the generated hypothetical answer.
4. The retrieved context is fed into the **Expanse AYA** LLM as part of the prompt.
5. The model generates a response based on the provided context, ensuring **accurate and reliable** answers.
   
## Possible Improvements
- Fine-tuning LLMs on medical data for better domain-specific performance.
- Enhancing retrieval efficiency with **multiple embeddings** and **specialized embedding models**.
- Implementing a **similarity threshold** to filter out unrelated documents and improve retrieval precision.

