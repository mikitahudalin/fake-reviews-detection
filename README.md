
# Fake Reviews Detection with Machine Learning Methods

**Author:** Mikita Hudalin

**Institution:** Warsaw University of Life Sciences (SGGW) – Institute of Technical Informatics

**Year:** 2025

---

## 📘 Overview

This work investigates the problem of **fake product reviews** on e-commerce platforms and explores the use of **machine learning (ML) methods** for their detection.

The thesis covers:

* Definitions and ethical implications of fake reviews
* Data collection and preprocessing
* Classical and modern ML algorithms for text classification
* Experimental comparison of different approaches
* Practical applications for **online content moderation** and **fraud prevention**

---

## 🎯 Objectives

* Develop a robust **ML-based system** for detecting fake reviews.
* Compare the effectiveness of different classifiers:
  * Logistic Regression
  * Random Forest
  * LSTM (Long Short-Term Memory networks)
  * BERT (Bidirectional Encoder Representations from Transformers)
* Identify best practices for preprocessing, training, and evaluation of text-based models.
* Evaluate **accuracy, recall, and AUC** to minimize misclassification of genuine reviews.

---

## 📊 Dataset

* **Source:** *Fake Reviews Dataset* (Salminen et al., 2022)
* **Size:** 40,432 reviews
* **Balance:** 50% real (Amazon reviews) / 50% fake (generated with GPT)
* **Features:**
  * `label` – CG (computer-generated) / OR (original human-written)
  * `category` – product category (10 Amazon categories)
  * `rating` – score (1–5)
  * `text` – review content

---

## ⚙️ Data Preprocessing

1. **Cleaning:**
   * Removed punctuation, symbols, emojis
   * Removed stopwords
   * Normalized casing
   * Lemmatization
2. **Tokenization:**
   * Split text into tokens for downstream analysis
3. **Numerical Representation:**
   * **TF-IDF** – vectorized word importance
   * **Word Embeddings** – semantic vector representations
   * **BERT embeddings** – contextual representations

---

## Machine Learning Methods

### 1. Classical Models

* **Logistic Regression** – simple, interpretable linear classifier
* **Random Forest** – ensemble method reducing overfitting

### 2. Deep Learning Models

* **LSTM** – sequence model handling word order and dependencies
* **BERT** – transformer-based contextual model pre-trained on large corpora

---

## 📈 Evaluation Metrics

* **Confusion Matrix** (TP, TN, FP, FN)
* **Accuracy** – percentage of correctly classified reviews
* **Precision & Recall** – balance false positives vs. false negatives
* **ROC & AUC** – ability to distinguish between classes

---

## Experiments & Results

### Logistic Regression

* Best hyperparameters: `C = 5`, `solver = liblinear`
* Accuracy: **88.6%** (test set)
* AUC:  **high** , strong generalization

### Random Forest

* Best hyperparameters: `n_estimators = 200`, `min_samples_leaf = 5`
* Accuracy: **84%** (test set)
* AUC: ~0.95
* Slight overfitting observed

### LSTM

* Best configuration: `128 units → dropout 0.5 → 64 units → dropout 0.3`
* Accuracy: **93.8%** (test set)
* AUC: **0.98**
* High performance, slight overfitting after 3rd epoch

### BERT

* Best configuration: `bert-base-uncased`, `padding=max_length`, `lr=2e-4`
* Accuracy: **91.3%** (test set, epoch 1)
* AUC: **0.975**
* Stable results across epochs, minor overfitting after epoch 3

---

## Key Findings

* **LSTM achieved the best overall accuracy (93.8%)** and strong AUC (0.98).
* **BERT performed slightly weaker in accuracy (91.3%) but showed high stability and contextual strength.**
* **Logistic Regression** provided solid baseline performance (88.6%), making it suitable for lightweight applications.
* **Random Forest** underperformed compared to neural approaches but still useful as an interpretable ensemble.

---

## Potencial Applications

* **E-commerce Platforms** – filtering fake reviews before publication
* **Reputation Management** – protecting brands from fraudulent manipulation
* **Recommender Systems** – improving personalization by excluding biased data
* **Regulatory Compliance** – assisting moderation teams in fraud detection

---

## Future Work

* Expand dataset with **multilingual reviews**
* Explore **hybrid models** (e.g., BERT + LSTM)
* Test robustness against **newer AI-generated content**
* Investigate **explainable AI (XAI)** for transparency in review classification

---

## 📚 References

The thesis cites key works in  **fake review detection** ,  **NLP methods** , and **ethical AI practices** including:

* Jindal & Liu (2008) – fake opinion definition
* Ott et al. (2011) – low-value positive reviews
* Mukherjee et al. (2012) – manipulative negative reviews
* Salminen et al. (2022) – dataset creation
* Rogers et al. (2021) – BERT applications in NLP
