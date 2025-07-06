# XB_0085 Text Mining for AI Project

---

## 📌 Overview

This repository showcases the final coursework for **XB_0085 Text Mining for AI**, completed at Vrije University in Spring 2024.

The project explores three core NLP tasks — **Sentiment Analysis**, **Topic Analysis**, and **Named Entity Recognition (NER)** — by applying both classical machine learning and modern transformer-based models.

---

## 👥 Contributors (Group 43)

- Arda Cem Çakmak
- Sinemis Toktaş
- Emre Akça
- Berk Yavaş

---

## 🗂️ Project Components


### 1️⃣ Sentiment Analysis

**Goal:**  
Classify text data into bipolar (positive/negative) or tripolar (positive/neutral/negative) sentiments.

**Methods Used:**  
- **Multinomial Naive Bayes Classifier (MNB):** Using `CountVectorizer` and `TfidfTransformer` from `scikit-learn`.  
- **VADER:** Initially tested but omitted from final metrics due to lower comparative performance.

**Experiments:**  
- **5 main experiments:**  
  - 2 bipolar (subjective/objective & positive/negative)
  - 3 tripolar (positive/neutral/negative)  
- `min_df` tuned from 1–20 for feature selection.  
- Best test accuracy: **0.7** on 30,000 balanced tweets (10,000 per sentiment).  
- Word clouds visualized frequent tokens for each sentiment.

**Key Observations:**  
- High precision for negative and neutral predictions.
- False positives mainly occurred due to overlapping tokens across sentiment classes.
- Limited neutral-labeled data restricted model performance.
- Data balance and larger training sets are crucial for higher accuracy.

**Datasets:**  
- [Cornell Movie Review Polarity Dataset](http://www.cs.cornell.edu/people/pabo/movie-review-data)
- [Cornell Subjectivity Dataset](http://www.cs.cornell.edu/people/pabo/movie-review-data)
- [Twitter Sentiment Dataset (3 Million Tweets)](https://www.kaggle.com/datasets/prkhrawsthi/twitter-sentiment-dataset-3-million-labelled-rows)
- [Sentiment Analysis Dataset](https://www.kaggle.com/datasets/abhi8923shriv/sentiment-analysis-dataset)

---

### 2️⃣ Topic Analysis

**Goal:**  
Categorize text data by topics — Books, Movies, Sports.

**Methods Used:**  
- **Multinomial Naive Bayes (MNB):** Probabilistic, assumes feature independence.
- **Support Vector Machine (SVM):** Margin-based classifier, robust for high-dimensional data.

**Datasets:**  
- [Amazon Book Reviews](https://www.kaggle.com/datasets/shrutimehta/amazon-book-reviews-webscraped)
- [IMDB Movie Reviews](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)
- [FIFA World Cup Tweets](https://www.kaggle.com/datasets/kumari2000/fifa-world-cup-twitter-dataset-2022)
- [European Football Tweets](https://www.kaggle.com/datasets/eliasdabbas/european-football-soccer-clubs-tweets)

**Results:**  
- **MNB:** High accuracy for Movies (~99%), limited by lower Book data.
- **SVM:** Outperformed MNB overall — up to 100% on test data with slight f1-score drop for Books.
- Richer sports datasets improved topic detection for SVM more than MNB.

**Challenges:**  
- Underrepresented Book data hindered overall balance.
- Future improvements: expand Book-related data, adjust class weights, enhance data quality.

---

### 3️⃣ Named Entity Recognition (NER)

**Goal:**  
Extract entities (e.g., PERSON, LOCATION, DATE, WORK_OF_ART) from text.

**Methods Used:**  
- **BERT:** Pre-trained on CoNLL-2003 dataset; 4 entity types.
- **Flair:** Pre-trained on OntoNotes 5.0; 18 entity types.

**Results:**  
- **BERT:** Accuracy ~0.87 — better performance but limited label set (mislabels extra categories as MISC).
- **Flair:** Broader entity coverage — accuracy ~0.78 — slightly lower due to tokenization edge cases and missing IOB tagging in raw output.

**Key Insights:**  
- BERT's bidirectional attention mechanism improved results despite label gaps.
- Flair's pre-trained extended label set gave it an edge on uncommon entities (DATE, WORK_OF_ART).
- Better token handling and additional fine-tuning could close performance gaps.

**Pre-trained Models:**  
- [Flair NER Model](https://huggingface.co/flair/ner-english-ontonotes-large)

---

## 🧩 Work Distribution

- **Arda Cem Çakmak:** Sentiment Analysis (Naive Bayes, VADER), analysis, poster design.
- **Sinemis Toktaş:** NERC (BERT, Flair), analysis, poster design.
- **Emre Akça:** Topic Analysis (Multinomial Naive Bayes), analysis, poster design.
- **Berk Yavaş:** Topic Analysis (SVM), analysis, poster design.

---

## 📌 Poster 

📄 **[Click to view our project poster](https://drive.google.com/file/d/1S-4dREroLCCN-YLNVEmaF-eiWcUQymsK/view?usp=sharing)**

---


## 🔗 Relevant Links

- [Multinomial Naive Bayes](https://scikit-learn.org/stable/modules/naive_bayes.html#multinomial-naive-bayes)
- [SVM Documentation](https://scikit-learn.org/stable/modules/svm.html)
- [OntoNotes 5.0 Corpus](https://catalog.ldc.upenn.edu/LDC2013T19)
- [Flair NER Pre-trained Model](https://huggingface.co/flair/ner-english-ontonotes-large)
- [Cornell Movie Review Data](http://www.cs.cornell.edu/people/pabo/movie-review-data)

---

## 📚 Acknowledgements

This project was conducted as part of XB_0085 Text Mining for AI at Vrije University.
We thank our instructor and TAs for their guidance and feedback throughout the course.
