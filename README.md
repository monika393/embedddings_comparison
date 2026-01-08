# Embeddings Through Time: From One-Hot to Transformer Embeddings

## Overview

This project demonstrates how text embeddings have evolved from early sparse
representations to modern contextual Transformer-based embeddings. Using a small,
carefully selected set of example words, the notebook visualizes how different
embedding techniques represent meaning, similarity, and context.

The notebook is designed to build intuition rather than optimize performance.
It is suitable for Google Colab, educational use, interviews, and GitHub showcasing.

---

## Purpose of This Notebook

Text embeddings are a foundational concept in natural language processing.
Different generations of embeddings make different assumptions about language:

- Early methods treat words as independent symbols
- Dense static embeddings capture similarity but not context
- Transformer embeddings model meaning dynamically based on context

This notebook compares these approaches side by side to answer questions such as:
- How do embedding geometries differ across methods?
- Why do static embeddings fail for ambiguous words?
- How do Transformers separate meaning using context?

---

## Embedding Methods Covered

The notebook compares the following embedding types:

### 1. One-Hot Encoding
- Sparse vector with one active dimension per word
- No notion of similarity or meaning
- Serves as a historical baseline

### 2. TF-IDF
- Sparse, corpus-based representation
- Captures term importance but not semantics
- Sentence-level representation

### 3. Word2Vec
- Dense, static word embeddings
- Learns similarity from local context
- Same vector for a word in all contexts

### 4. FastText
- Dense, static embeddings with subword information
- Handles rare words and morphology better than Word2Vec

### 5. GloVe
- Dense, static pretrained embeddings
- Trained on large global co-occurrence statistics

### 6. BERT Token Embeddings
- Contextual embeddings at the token level
- Same word receives different vectors depending on sentence context

### 7. Sentence-Transformer Embeddings
- Contextual sentence-level embeddings
- Optimized for semantic similarity and clustering

---

## Word and Context Selection

Six base words are selected to demonstrate both semantic similarity and ambiguity:

- bank
- money
- river
- python
- snake
- code

To highlight contextual behavior, two ambiguous words are used in two different contexts:

- bank (financial institution vs river bank)
- python (programming language vs animal)

This results in eight plotted points:

- bank_finance
- bank_river
- python_programming
- python_animal
- money
- river
- snake
- code

This setup clearly shows the limitations of static embeddings and the strengths of
contextual Transformer embeddings.

---

## Visualization Approach

For each embedding method:

1. Embeddings are computed for all items
2. High-dimensional vectors are reduced to 2D using PCA
3. Points are plotted in a scatter plot with text labels
4. All embedding types are displayed in a single multi-panel figure

Points are color-coded into semantic categories to provide a meaningful legend:

- Finance: bank_finance, money
- Nature: bank_river, river, snake, python_animal
- Technology: python_programming, code

This makes it easy to visually evaluate whether embeddings cluster related concepts.

---

## Notebook Structure

The notebook is organized into the following sections:

1. Setup and dependency installation
2. Definition of words, contexts, and corpus
3. One-hot embeddings
4. TF-IDF embeddings
5. Word2Vec embeddings (trained)
6. FastText embeddings (trained)
7. GloVe embeddings (pretrained)
8. BERT token-level embeddings
9. Sentence-Transformer embeddings
10. PCA-based visualization
11. Combined multi-panel plot with legend

Each section includes detailed comments explaining both the code and the underlying concept.

---

## How to Run

### Google Colab (Recommended)

1. Open Google Colab
2. Upload the notebook or clone the repository
3. Run all cells from top to bottom
4. Plots will be generated automatically

### Local Execution (Optional)

```bash
pip install gensim transformers sentence-transformers scikit-learn matplotlib numpy torch
jupyter notebook
