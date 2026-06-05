# Psar: E-Commerce Inquiry Intelligence

Psar (ផ្សារ — market in Khmer) is an AI-powered
inquiry intelligence system for Cambodian social
commerce. It combines TF-IDF intent classification,
CatBoost, and RAG-based product retrieval to answer
buyer questions and manage live inventory.

## Directory Structure
psar/
├── code/       # notebooks
├── data/       # input datasets
├── output/     # figures and results
└── README.md

## Notebook

### 00_psar_inquiry_intelligence.ipynb
- Inputs: ../data/psar_catalog.csv,
  ../data/psar_queries.csv
- Function: Full end-to-end pipeline including
  data loading, product object construction,
  live inventory initialization, TF-IDF vectorization,
  Logistic Regression and CatBoost intent
  classification, rule-based entity extraction,
  SentenceTransformer embeddings, cosine similarity
  product retrieval, inventory-grounded answer
  generation, multi-turn chatbot memory,
  20 structured inventory trials, and
  result visualization
- Outputs: trial_df, purchase_df, stock_audit_df,
  f1.png, inventory_depletion.png,
  inventory_trials.png, rag_retrieval.png

## Data
- psar_catalog.csv: 300 products across Clothing,
  Shoes, and Accessories with stock by size
- psar_queries.csv: 360 labeled queries across
  6 intent classes

## Models
- Logistic Regression: 98.15% accuracy (baseline)
- CatBoost: 99.07% accuracy (primary classifier)

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
