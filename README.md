# Stardew Valley LLM

Stardew Valley LLM is an LLM utilizing Retrieval-Augmented Generation to infer answers to questions based on the online Stardew Valley Wiki.

## Features

- Up-to-date responses based on live data
- Contextual answers leveraging the Stardew Valley Wiki

<!--
## Running

Instructions for running the project will be provided here.
-->

## Process

### Training Method

One of the biggest weaknesses of Large Language Models (LLMs) in AI is their ability to answer questions based on the most recent data available, as training and fine-tuning can take significant time before release. Retrieval-Augmented Generation allows the model to generate up-to-date responses by pulling data from a live/dynamic source. This enables the model to maintain accuracy as the knowledge source changes without needing to retrain the LLM. This feature inspired the creation of this project as a proof of concept.

### Choosing the Data Source

The Stardew Valley Wiki encourages users to view the already formatted sources for each page, eliminating the need to contact the author.

### Embedding Model

The embedding model assigns vectors to the text, allowing the model to select the closest (“most relevant”) chunk of information to the prompt. For each chunk, both the embedding and the source text are stored. The model also creates an embedding of the prompt. To accommodate thousands of vectors, these chunks are stored in a vector database. A query to the database retrieves the top similar chunks related to the prompt. The results of this query are then added to the prompt given to the LLM, enabling the model to answer within the ***context*** of the closest/most relevant information, ***inferring*** answers to questions without fine-tuning.

### Vector Database

The database chosen for this project is the Chroma Database, selected for its popularity and availability of tutorials.
