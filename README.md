# Text Classification with Word2Vec and Averaged Embeddings

This repository demonstrates a straightforward approach to binary text classification using Word2Vec-generated embeddings and an averaged-word-vector model.

---

## Overview

The goal is to **classify text messages (spam vs. ham)** by leveraging unsupervised word embeddings (Word2Vec), averaging them into fixed-length vectors for each message, and then training a machine learning classifier on these representations.

---

## Approach

1. **Data Preparation**  
   - Load and clean the dataset (e.g., SMS spam collection).  
   - Preprocess text: tokenization, lowercasing, stop‑word removal.

2. **Word2Vec Embeddings**  
   - Train a Word2Vec model on the cleaned text using Gensim’s `Word2Vec` (skip‑gram or CBOW).  
   - This yields vector representations for each word in your vocabulary.

3. **Message Vectorization**  
   - Convert each message into a fixed-size vector by averaging its individual word vectors.  
   - Messages with no known words are represented by all-zero vectors.

4. **Train Classifier**  
   - Use the averaged vectors to train a classifier (e.g., `RandomForestClassifier`).

5. **Evaluate**  
   - Predict on a held-out test set and compute metrics like precision, recall, and accuracy.

---

## Installation & Requirements

Install dependencies using:

```bash
pip install -r requirements.txt
```

Key libraries include: `gensim`, `numpy`, `pandas`, `scikit-learn`.

---

## Usage

Here's how to run the full pipeline:

```bash
python main.py
```

This script:

- Trains Word2Vec.
- Computes averaged vectors.
- Trains and evaluates the classifier.

---

## File Structure

- `main.py`: Full pipeline execution.
- `word2vec_utils.py`: Handles training Word2Vec and vector averaging.
- `classifier.py`: Contains classifier training and evaluation logic.
- `data/`: Contains raw and processed data (e.g., `spam.csv`).
- `requirements.txt`: Lists Python dependencies.

---

## Results

Typical performance on an SMS spam dataset:

```
Precision: 0.97 | Recall: 0.99 | Accuracy: 0.97
```

---

## Further Enhancements

- Use **pre‑trained embeddings** (e.g., Google News, GloVe).
- Try **TF‑IDF‑weighted averaging** for improved representations.
- Explore deep models: CNNs, RNNs, transformer‑based architectures.
- Experiment with alternative classifiers: SVM, Logistic Regression, XGBoost.

---

## Learn More

- Word2Vec: skip‑gram vs. CBOW  
- Averaged embeddings for classification  
- Using pre‑trained Word2Vec/GloVe vectors

---

## License

This project is licensed under the **MIT License**—see `LICENSE` for details.
