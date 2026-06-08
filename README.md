# Psar: E-Commerce Inquiry Intelligence

Psar (ផ្សារ | meaning "market" in Khmer) is an AI-powered inquiry intelligence system for Cambodian social commerce. It combines intent classification,
CatBoost and RAG to retrieve answers to buyer questions. 

## Directory Structure
psar/
├── code/       #jupyter notebook
├── data/       #datasets (catalog, queries)
├── output/     #figures
└── README.md 

### 00_psar_inquiry_intelligence.ipynb
- Inputs: ../data/psar_catalog.csv, ../data/psar_queries.csv
- It is the full end-to-end pipeline for the Psar system, including data loading, product object construction,live inventory initialization, TF-IDF vectorization,
Logistic Regression and CatBoost intent, classification, rule-based entity extraction, SentenceTransformer embeddings, cosine similarity, product retrieval
- The section Chatbot is an integrated chatbot in which you can test Psar and try to ask questions about any products. A set of Recommended Live Demo Questions is included. 

## Data
- psar_catalog.csv. This dataset consists of 300 products with various information about each product, such as price, size, and color. 
- psar_queries.csv. This is a dataset of 360 queries. The six intent classes
are price inquiry, availability check, size question, product search, complex multicriteria, and other.

## Output
- Results for Logistic Regression is 98.15% accuracy, and CatBoost is 99.07% accuracy
- 4 figures 

## Pipeline
Customer query
→ TF-IDF vectorization
→ CatBoost intent classification
→ Rule-based entity extraction
→ SentenceTransformer product retrieval
→ Inventory stock check
→ Grounded answer generation
→ Real-time inventory update

## Results
- Intent classification: 99.07% accuracy (CatBoost)
- RAG retrieval: 90% accuracy across 20 trials
- Inventory trials: 7 successful purchases,
  1 failed (insufficient stock)

## Requirements
pandas, numpy, scikit-learn, catboost,
sentence-transformers, torch, matplotlib

## Author
SaraVotey Mom — QSS 45, 2026
