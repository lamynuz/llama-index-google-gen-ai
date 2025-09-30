# Question-Answering with LlamaIndex and Gemini

This project is a question-answering system built with **LlamaIndex** and powered by **Google's Gemini** models.

It demonstrates how to create a simple Retrieval-Augmented Generation (RAG) pipeline. The notebook loads documents from a local directory, embeds them into a vector space, and then uses a query engine to answer questions based on the content of those documents.

***

## How it works

* **Document Loading**: The notebook starts by loading local documents (like `.pdf` or `.docx` files) from a `data` directory using `SimpleDirectoryReader`.
* **Model Configuration**: It configures LlamaIndex to use Google's Gemini models for both the language model (`gemini-2.0-flash`) and the embedding model (`gemini-embedding-001`).
* **Indexing**: The loaded documents are then converted into a `VectorStoreIndex`. This process involves splitting the text into chunks and creating vector embeddings for each chunk, making the content searchable.
* **Persistence**: The created index is saved to disk in a `storage` directory. This allows you to load the index later without having to re-process the documents.
* **Querying**: Finally, a `query_engine` is created from the index to ask questions. The system finds the most relevant document chunks for a given question and uses the Gemini model to generate a natural language answer.

***

## Pre-requisites:
* **Google API Key**: Have a key loaded in an .env file
* **Documents**: Have documents (like `.pdf` or `.docx` files) in the folder `data`
