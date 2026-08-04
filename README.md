# 💄 Amazon Luxury Beauty Reviews - Natural Language Processing (NLP) Analysis

An end-to-end **Natural Language Processing (NLP)** project analysing Amazon **Luxury Beauty** customer reviews. This project demonstrates how unstructured customer feedback can be transformed into meaningful business insights through text preprocessing, sentiment analysis, Named Entity Recognition (NER), and topic modelling.

---

## 🚀 Project Overview

Customer reviews provide valuable information about product quality, customer satisfaction, and consumer preferences. This project applies several NLP techniques to thousands of Amazon Luxury Beauty reviews to answer key business questions:

- What overall sentiment do customers express?
- Which words and product features appear most frequently?
- Which brands, products, and entities are commonly mentioned?
- What major discussion topics emerge from customer reviews?

The project demonstrates a complete NLP workflow, from raw text preprocessing to business insight generation.

---

## 📂 Dataset

**Source:** Amazon Review Dataset (UCSD)

https://cseweb.ucsd.edu/~jmcauley/datasets/amazon_v2/

### Dataset Used

- **Luxury_Beauty_5.json.gz**
- Amazon Luxury Beauty Reviews
- Review period: **May 1996 – October 2018**

The Luxury Beauty category was selected because luxury products typically have higher profit margins, making customer sentiment and brand perception especially valuable for business decision-making.

---

## 🛠️ Tech Stack & Libraries

**Language**

- Python

**Libraries**

- Pandas
- NumPy
- NLTK
- TextBlob
- SpaCy
- Scikit-learn
- WordCloud
- Matplotlib
- pyLDAvis

---

## 🧹 NLP Pipeline

The project follows the workflow below:

```text
Amazon Review Dataset
        │
        ▼
Dataset Preparation
        │
        ▼
Text Preprocessing
        │
        ▼
Vocabulary Building
        │
        ▼
Word Cloud Visualization
        │
        ▼
Sentiment Analysis
        │
        ▼
Named Entity Recognition (NER)
        │
        ▼
Topic Modelling (LDA)
        │
        ▼
Business Insights
```

---

## 🔍 Data Preparation & Preprocessing

The Amazon Luxury Beauty dataset was loaded from the compressed JSON file and converted into a Pandas DataFrame.

Before analysis, the review text was cleaned using several preprocessing techniques:

- Convert text to lowercase
- Remove punctuation and special characters
- Remove extra whitespace
- Keep alphabetic characters only
- Tokenization
- Stopword removal
- Stemming
- Lemmatization

These preprocessing steps standardize customer reviews and improve the quality of downstream NLP tasks.

---

# 📈 Key Findings & Visualizations

## 1. Vocabulary Analysis

A vocabulary was built from the cleaned review text to identify the most frequently occurring words across customer reviews.

A **WordCloud** was generated to provide a visual summary of the vocabulary used throughout the Luxury Beauty category. Larger words indicate higher frequency, making it easier to identify commonly discussed products, product characteristics, and customer experiences.

![WordCloud](images/wordcloud.png)

---

## 2. Sentiment Analysis

Customer sentiment was evaluated using **TextBlob**, assigning each review a polarity score between:

- **-1** → Negative
- **0** → Neutral
- **+1** → Positive

A histogram was generated using **Matplotlib** to visualize the overall sentiment distribution across all reviews.

The project also compares textual sentiment with customers' numerical star ratings to determine whether review sentiment aligns with product ratings.

![Sentiment Distribution](images/sentiment_histogram.png)

---

## 3. Named Entity Recognition (NER)

Named Entity Recognition was performed using **SpaCy's pretrained English model (`en_core_web_sm`)**.

The extracted entities include:

- Organizations
- Products
- People
- Locations
- Dates
- Quantities
- Monetary values

NER transforms unstructured customer reviews into structured information, enabling businesses to identify frequently mentioned brands, products, and other important entities.

![Named Entity Recognition](images/ner_visualization.png)

---

## 4. Topic Modelling

Latent Dirichlet Allocation (**LDA**) was applied to discover hidden discussion topics across thousands of customer reviews.

The topic modelling workflow included:

- Creating a document-term matrix using `CountVectorizer`
- Training an LDA model with **5 topics**
- Assigning each review to its dominant topic
- Extracting representative keywords for every topic

Finally, **pyLDAvis** was used to visualize topic distributions and keyword importance interactively.

![LDA Topic Modelling](images/lda_visualization.png)

> **Interactive Version:** Open `images/lda_visualization.html` locally to explore the interactive pyLDAvis visualization.

---

# 💡 Business Insights

The NLP pipeline provides several valuable business insights, including:

- Overall customer sentiment towards Luxury Beauty products
- Agreement between review sentiment and customer ratings
- Frequently discussed product features and characteristics
- Important named entities such as brands, products, and organizations
- Hidden discussion topics across thousands of customer reviews

These insights can help businesses:

- Improve product quality
- Monitor customer satisfaction
- Understand customer preferences
- Enhance marketing strategies
- Support data-driven business decisions

---

## 📁 Project Structure

```text
├── Luxury_Beauty_5.json.gz
├── NLP_Project.ipynb
├── README.md
├── images/
│   ├── wordcloud.png
│   ├── sentiment_histogram.png
│   ├── ner_visualization.png
│   ├── lda_visualization.png
│   └── lda_visualization.html
```

---

## 📚 Sample Libraries Used

```python
import pandas as pd
import numpy as np
import nltk
import spacy
from textblob import TextBlob
from wordcloud import WordCloud
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.decomposition import LatentDirichletAllocation
import pyLDAvis
```

---

## 🎯 Key Learning Outcomes

Through this project, I gained practical experience in:

- Building an end-to-end NLP pipeline
- Cleaning and preprocessing large text datasets
- Performing sentiment analysis using TextBlob
- Applying Named Entity Recognition using SpaCy
- Discovering hidden topics using LDA topic modelling
- Visualizing NLP outputs using WordCloud, Matplotlib, and pyLDAvis
- Transforming unstructured customer reviews into actionable business insights

---

## 🚀 Future Improvements

Potential future enhancements include:

- Applying transformer-based sentiment models (e.g., BERT or RoBERTa)
- Performing aspect-based sentiment analysis
- Fine-tuning SpaCy's NER model for e-commerce-specific entities
- Comparing alternative topic modelling techniques such as BERTopic and NMF
- Building an interactive dashboard using Streamlit or Dash

---

## 👤 Author

This project was completed as part of a Natural Language Processing (NLP) coursework assignment, demonstrating the practical application of NLP techniques on real-world Amazon customer review data.
