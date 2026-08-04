# Amazon Luxury Beauty Reviews - Natural Language Processing (NLP) Analysis

## Project Overview

This project demonstrates the application of **Natural Language Processing (NLP)** techniques to analyze customer reviews from Amazon's **Luxury Beauty** product category.

The objective is to transform thousands of unstructured customer reviews into meaningful business insights that can help Amazon better understand customer sentiment, identify commonly discussed product features, and discover major discussion topics.

The project uses the **Amazon Review Dataset (UCSD)** and applies several NLP techniques including text preprocessing, vocabulary building, sentiment analysis, Named Entity Recognition (NER), and topic modelling.

---

## Dataset

**Dataset Source**

Amazon Review Dataset (UCSD)

https://cseweb.ucsd.edu/~jmcauley/datasets/amazon_v2/

### Selected Dataset

- Luxury_Beauty_5.json.gz
- Amazon Luxury Beauty Reviews
- Reviews collected between **May 1996 – October 2018**

The Luxury Beauty category was selected because luxury products typically have higher profit margins, making customer sentiment and brand perception especially valuable for business decision making.

---

# Project Workflow

The project follows a complete NLP pipeline:

```
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

# Technologies Used

- Python
- Pandas
- NumPy
- NLTK
- TextBlob
- SpaCy
- Scikit-learn
- WordCloud
- Matplotlib
- Seaborn
- pyLDAvis

---

# NLP Techniques Implemented

## 1. Dataset Preparation

The Amazon Luxury Beauty dataset was loaded from the compressed JSON file and converted into a Pandas DataFrame.

The review text (`reviewText`) was selected as the primary field for NLP analysis.

---

## 2. Text Preprocessing

A preprocessing pipeline was created to clean the review text before applying NLP techniques.

The preprocessing steps include:

- Convert text to lowercase
- Remove extra whitespace
- Remove punctuation and special characters
- Keep alphabetic characters only
- Tokenization
- Stopword removal
- Stemming
- Lemmatization

This process standardizes the text and improves the quality of downstream NLP tasks.

---

## 3. Vocabulary Building

After preprocessing, a vocabulary was constructed from the cleaned review text.

This allows the NLP models to understand the collection of unique words appearing in customer reviews.

A **WordCloud** was also generated to visualize the most frequently occurring words within the Luxury Beauty reviews.

Commonly appearing words included terms related to skincare, beauty products, and customer experiences.

---

## 4. Sentiment Analysis

Customer sentiment was evaluated using **TextBlob**.

Each review was assigned a polarity score ranging from:

- **-1** → Negative
- **0** → Neutral
- **+1** → Positive

A histogram was generated to visualize the distribution of sentiment across all reviews.

The project also compared sentiment polarity with customers' numerical ratings to evaluate whether textual sentiment aligns with star ratings.

---

## 5. Named Entity Recognition (NER)

Named Entity Recognition was performed using **SpaCy's pretrained English model (`en_core_web_sm`)**.

Entities extracted include:

- Organizations
- Products
- Locations
- Dates
- People
- Quantities
- Monetary values

NER helps transform unstructured customer reviews into structured information, allowing businesses to identify frequently mentioned brands, products, and other important entities.

---

## 6. Topic Modelling

Latent Dirichlet Allocation (**LDA**) was used to discover hidden topics discussed within customer reviews.

Steps performed include:

- Convert reviews into document-term matrices using CountVectorizer
- Train an LDA model with **5 topics**
- Assign each review to its dominant topic
- Extract the top keywords representing each topic

Finally, **pyLDAvis** was used to visualize topic distributions and keyword importance interactively.

---

# Project Results

The NLP pipeline provides several business insights, including:

- Overall customer sentiment towards Luxury Beauty products
- Agreement between review sentiment and product ratings
- Frequently discussed product features
- Important named entities mentioned by customers
- Major discussion topics across thousands of reviews

These insights can help businesses:

- Improve products
- Monitor customer satisfaction
- Understand customer preferences
- Enhance marketing strategies
- Support data-driven business decisions

---

# Project Structure

```
├── Luxury_Beauty_5.json.gz
├── NLP_Project.ipynb
├── README.md
├── images/
│   ├── wordcloud.png
│   ├── sentiment_histogram.png
│   └── lda_visualization.png
```

---

# Sample Libraries Used

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

# Key Learning Outcomes

Through this project, I learned how to:

- Build an end-to-end NLP pipeline
- Clean and preprocess large text datasets
- Perform sentiment analysis using TextBlob
- Apply Named Entity Recognition using SpaCy
- Discover hidden topics using LDA topic modelling
- Visualize NLP outputs using WordCloud and pyLDAvis
- Transform unstructured customer reviews into actionable business insights

---

# Future Improvements

Potential improvements include:

- Using transformer-based sentiment models (e.g., BERT or RoBERTa)
- Fine-tuning SpaCy's NER model for e-commerce-specific entities
- Performing aspect-based sentiment analysis
- Comparing multiple topic modelling algorithms (LDA, NMF, BERTopic)
- Building an interactive dashboard using Streamlit or Dash

---

# Author

This project was completed as part of a Natural Language Processing (NLP) coursework assignment demonstrating the practical application of NLP techniques on real-world Amazon customer review data.
