# Book Reviews Similarity

Project overview
- This repository contains Jupyter Notebooks implementing exploratory analysis and similarity models for book reviews. The goal is to compute, visualize, and evaluate textual similarity between reviews (or books) to support tasks like recommendation, duplicate detection, and content clustering.

Key features
- Data cleaning and preprocessing of review text.
- Multiple textual representations: TF-IDF, word embeddings, sentence embeddings (e.g., SBERT).
- Pairwise similarity computations (cosine similarity, dot product) and nearest-neighbor search.
- Visualizations: heatmaps, nearest-neighbor examples, dimensionality reduction (UMAP / t-SNE).
- Example notebook(s) showing how to query similar reviews/books interactively.

Repository structure
- notebooks/ — Jupyter notebooks with EDA, modeling and examples.
- data/ — (optional) sample or preprocessed datasets (not included if large).
- notebooks/00-README-and-setup.ipynb — a starting notebook describing how to run the analyses.

Data
- Expected data format: CSV/JSON with at least columns: review_id, book_id, review_text, reviewer_id, rating, date.
- If using a public dataset (Amazon, Goodreads), include a readme in data/ with download instructions and a note about licensing and size.
- Notebooks contain examples using a subset or synthetic sample if full data is not included.

Getting started — quick steps
1. Clone the repository:
   git clone https://github.com/Dona134/Book-Reviews-Similarity.git
2. Create a Python environment (recommended):
   python -m venv .venv
   source .venv/bin/activate  # Windows: .venv\Scripts\activate
3. Install dependencies:
   pip install -r requirements.txt
   If requirements.txt is not present, see the Requirements section below.
4. Open notebooks in Jupyter / JupyterLab and run cells in order:
   jupyter lab

Requirements
- Python 3.8+
- Jupyter Notebook or JupyterLab
- pandas, numpy
- scikit-learn
- sentence-transformers (for SBERT embeddings) or gensim
- umap-learn (optional for embeddings visualization)
- matplotlib / seaborn / plotly for visualization
- faiss-cpu or annoy (optional) for fast nearest-neighbor search

Example notebooks
- 01-data-cleaning.ipynb — load and clean reviews.
- 02-embeddings.ipynb — compute and save embeddings (TF-IDF, SBERT).
- 03-similarity-search.ipynb — compute similarity matrices and query nearest neighbors.
- 04-visualization.ipynb — UMAP/t-SNE visualizations and heatmaps.

How to reproduce
- Provide or download the dataset used (see data/README if present).
- Run notebooks sequentially. Notebooks save intermediate outputs (embeddings, indices) to data/processed/ to avoid recomputing heavy steps.
- For large datasets, use batch embedding and a vector index (FAISS) for nearest-neighbor lookup.

Notes on performance
- Embedding models (SBERT) are more accurate but slower and require more memory than TF-IDF.
- Use GPU for faster embeddings if available (sentence-transformers supports PyTorch GPU).

Evaluation
- If labeled similar/dissimilar pairs exist, use precision@k, recall@k, MAP to evaluate retrieval.
- For clustering use silhouette score, Davies-Bouldin, or human qualitative inspection.

Extending this project
- Add a web demo to query for similar reviews in real time.
- Experiment with transformer fine-tuning to adapt embeddings to book-review semantics.
- Integrate recommendation logic (combine similarity with popularity-based factors).

License
- Add a LICENSE file to the repo. MIT is a common choice for analysis projects:
  See the LICENSE file in this repository for details.

Contributing
- Open issues to propose improvements.
- Follow the notebook style and add a new notebook or script for major new analyses.

Contact
- Owner: Dona134 (GitHub)
- For questions, open an issue or email the repository owner if an email is provided.
