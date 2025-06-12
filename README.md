# Data Mining Project: Information Retrieval with Query Expansion and Evaluation

This project focuses on building a full-featured Information Retrieval (IR) system using the **Vaswani dataset**. It includes data collection, preprocessing, indexing, query processing, expansion using various embedding models, evaluation, and a simple web interface for user interaction.

---

##  Project Features

- Document and query handling using `ir_datasets`
- Text preprocessing (cleaning, tokenization, stop word removal, stemming)
- Inverted index construction
- Query preprocessing and TF-IDF based ranking
- Query expansion using:
  - GloVe word embeddings
  - ELMo contextual embeddings
  - BERT embeddings
- Retrieval performance evaluation (Precision, Recall, MAP)
- Flask-based web interface for searching documents

---

##  Project Structure

📁 data_mining_ir_project/
│
├── app.py # Flask web application
├── index.py # Code for indexing and inverted index creation
├── preprocess.py # Text preprocessing functions
├── retrieval.py # Query processing and TF-IDF ranking
├── expansion.py # Query expansion using RM3, GloVe, ELMo, BERT
├── evaluation.py # Evaluation metrics (Precision, Recall)
├── README.md # This file
└── requirements.txt # Python dependencies


##  Methodology

### 1. Data Collection
- Downloaded the Vaswani dataset using `ir_datasets`.
- Extracted documents, queries, and Qrels.
- Stored data into `pandas` DataFrames for easier manipulation.

### 2. Preprocessing
- Performed standard preprocessing:
  - Lowercasing
  - Tokenization
  - Stop word removal
  - Stemming
  - Cleaning special characters and whitespace

### 3. Indexing
- Constructed an inverted index mapping each term to:
  - Document IDs it appears in
  - Term frequency per document

### 4.  Query Processing
- Preprocessed user queries in the same way as documents.
- Applied TF-IDF ranking to score documents for each query.

### 5.  Query Expansion
- Used **Relevance Feedback (RM3)** to improve query performance by analyzing top-ranked documents.
- Integrated **embedding models** for semantic similarity:
  - GloVe
  - ELMo
  - BERT
- Expanded the queries using semantically similar terms.

### 6. Evaluation
- Compared retrieved results with ground truth using Qrels.
- Calculated:
  - **Precision**
  - **Recall**
  - **Mean Average Precision (MAP)**

### 7. Web Interface
- Built with **Flask**.
- Features:
  - Homepage for entering queries
  - Results page displaying ranked document matches
  - Integrated backend logic for query preprocessing, expansion, and retrieval

---

##  Running the Project

### Requirements
Install the required packages:
```bash
pip install -r requirements.txt

▶ Start the Flask App

python app.py

Visit http://127.0.0.1:5000 in your browser.
Sample Use Case

    User enters a query such as:

    neural network applications

    Query is preprocessed and expanded using RM3 and embedding models.

    TF-IDF model retrieves relevant documents.

    Evaluation metrics are computed using Qrels.

    Results are displayed on the web interface.

Results Summary

    Improved retrieval quality using query expansion techniques.

    Semantic embeddings helped enhance query understanding.

    Evaluation metrics provided insights into the performance of each method.

 References

    ir_datasets

    GloVe Embeddings

    ELMo

    BERT

    TF-IDF

    Flask
