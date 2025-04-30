# Sentiment Analysis using Traditional and Sentiment-Enhanced Embeddings

This project explores a deep learning pipeline for multilingual sentiment analysis using traditional word embeddings (Word2Vec, GloVe, FastText) and sentiment-enhanced embeddings. It demonstrates performance on both high-resource (English - IMDB) and low-resource (Marathi - MahaSent) datasets.

---

## 📊 Overview

The proposed system performs sentiment classification using LSTM-based models enhanced by rich text embeddings. A complete pipeline from data preprocessing to evaluation is implemented with a focus on multilingual and sentiment-specific representation.


## 📁 Datasets

### 1. **IMDB Dataset**
- 50,000 English movie reviews
- Balanced for binary sentiment classification (positive/negative)

### 2. **MahaSent Dataset**
- Marathi-language sentiment dataset
- Includes news articles, tweets, reviews
- Multi-domain and morphologically rich

---

## 🔄 Preprocessing Pipeline

- **Text Cleaning:** Remove HTML, special characters, stopwords
- **Tokenization & Lowercasing**
- **Class Balancing:** Using oversampling, undersampling, or SMOTE
- **Marathi Text Normalization:** Transliteration and stemming for morphology handling

---

## 🔠 Embedding Techniques

- **Word2Vec:** Contextual learning via CBOW & Skip-Gram
- **GloVe:** Global vectors from word co-occurrence
- **FastText:** Subword-level embeddings for rare/morphologically rich words

---

## ❤️ Sentiment-Enhanced Embeddings

- Pre-trained on sentiment-labeled corpora
- Integrates sentiment lexicons and polarity scores
- Captures emotion-specific and contextual patterns
- Fed into an LSTM classifier for improved performance

---

## 🤖 Sentiment Classification Model

- **Architecture:** LSTM with dropout & softmax
- **Inputs:** Traditional or Sentiment-Enhanced embeddings
- **Advantages:** Handles sequential context and long-term dependencies

---

## 📈 Evaluation Metrics

- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**

Each embedding model was evaluated on both IMDB and MahaSent datasets.

---

## 📊 Results Summary

### **IMDB Dataset (English)**

| Model                   | Accuracy | Precision | Recall  | F1-Score |
|------------------------|----------|-----------|---------|----------|
| Word2Vec               | 57.01%   | 54.55%    | 84.12%  | 66.18%   |
| GloVe                  | 84.85%   | 80.89%    | 91.26%  | 85.76%   |
| FastText               | 57.52%   | 54.71%    | 87.27%  | 67.20%   |
| Sentiment-Enhanced LSTM| 51.16%   | 67.20%    | 51.53%  | 39.31%   |

#### 🔍 Analysis:
- **GloVe** performed best overall on English.
- **FastText** handled subword and rare terms better.
- **Sentiment-enhanced embeddings** captured subtle sentiments but lacked generalization due to limited training corpus.

---

### **MahaSent Dataset (Marathi)**

| Model                   | Accuracy | Precision | Recall  | F1-Score |
|------------------------|----------|-----------|---------|----------|
| Word2Vec               | 50%      | 75%       | 50%     | 60%      |
| GloVe                  | 50%      | 75%       | 33.33%  | 50%      |
| FastText               | 33.33%   | 50%       | 75%     | 60%      |
| Sentiment-Enhanced LSTM| 78%      | 78%       | 78%     | 78%      |

#### 🔍 Analysis:
- Traditional embeddings struggled with Marathi's complexity.
- **Sentiment-enhanced LSTM** clearly outperformed all others by addressing cultural and linguistic subtleties.

---

## 📌 Conclusion

This project demonstrates:
- The effectiveness of combining contextual and sentiment-aware representations.
- The need for language-specific customization in low-resource settings.
- That sentiment-enhanced embeddings can significantly improve performance for morphologically rich and low-resource languages.

---

## 🧠 Future Work

- Integrate attention mechanisms for better interpretability
- Expand the Marathi corpus
- Experiment with transformer-based multilingual embeddings (e.g., mBERT, XLM-R)

