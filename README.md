# Amazon Luxury Beauty Reviews - Natural Language Processing (NLP) Analysis

## Project Overview

This project demonstrates the application of **Natural Language Processing (NLP)** techniques to analyze customer reviews from Amazon's **Luxury Beauty** product category.

Using the **Amazon Review Dataset (UCSD)**, the project transforms thousands of unstructured customer reviews into meaningful business insights. The analysis focuses on understanding customer sentiment, identifying frequently discussed product features, extracting named entities, and discovering hidden discussion topics through topic modelling.

The project implements a complete end-to-end NLP pipeline, from data preprocessing to visualization, using Python and popular NLP libraries.

---

# Dataset

## Dataset Source

**Amazon Review Dataset (UCSD)**

https://cseweb.ucsd.edu/~jmcauley/datasets/amazon_v2/

### Selected Dataset

- **Luxury_Beauty_5.json.gz**
- Amazon Luxury Beauty Reviews
- Reviews collected between **May 1996 – October 2018**

The Luxury Beauty category was selected because luxury products generally have higher profit margins, making customer feedback and brand perception especially valuable for business decision-making.

---

# Project Workflow

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

The Amazon Luxury Beauty dataset was loaded from the compressed JSON file (`Luxury_Beauty_5.json.gz`) and converted into a Pandas DataFrame.

The review text (`reviewText`) was selected as the primary feature for subsequent NLP analysis.

---

## 2. Text Preprocessing

A preprocessing pipeline was developed to clean and standardize customer reviews before analysis.

The preprocessing steps include:

- Convert text to lowercase
- Remove extra whitespace
- Remove punctuation and special characters
- Keep alphabetic characters only
- Tokenization
- Stopword removal
- Stemming
- Lemmatization

These preprocessing steps reduce noise and improve the performance of downstream NLP models.

---

## 3. Vocabulary Building

After preprocessing, a vocabulary was constructed from the cleaned review text.

A **WordCloud** was generated to visualize the most frequently occurring words across customer reviews. Frequently appearing words highlight common product characteristics, customer experiences, and recurring discussion themes.

<p align="center">
  <a href="images/wordcloud.png">
    <img src="images/wordcloud.png" width="750">
  </a>
</p>

<p align="center">
<i>Figure 1. WordCloud generated from the preprocessed Amazon Luxury Beauty reviews (click the image to enlarge).</i>
</p>

---

## 4. Sentiment Analysis

Customer sentiment was evaluated using **TextBlob**, which assigns each review a sentiment polarity score ranging from:

- **-1** → Negative
- **0** → Neutral
- **+1** → Positive

A histogram was generated using **Matplotlib** to visualize the overall sentiment distribution across all reviews.

The project also compares sentiment polarity with customers' numerical star ratings to determine whether textual sentiment aligns with product ratings.

<p align="center">
  <a href="images/sentiment_histogram.png">
    <img src="images/sentiment_histogram.png" width="700">
  </a>
</p>

<p align="center">
<i>Figure 2. Distribution of sentiment polarity across Amazon Luxury Beauty reviews (click the image to enlarge).</i>
</p>

---

## 5. Named Entity Recognition (NER)

Named Entity Recognition (NER) was performed using **SpaCy's pretrained English model (`en_core_web_sm`)**.

The extracted entities include:

- Organizations
- Products
- Locations
- Dates
- People
- Quantities
- Monetary values

NER transforms unstructured customer reviews into structured information by identifying important entities frequently mentioned throughout the dataset.

<p align="center">
  <a href="images/ner_visualization.png">
    <img src="images/ner_visualization.png" width="850">
  </a>
</p>

<p align="center">
<i>Figure 3. Example output of SpaCy Named Entity Recognition (click the image to enlarge).</i>
</p>

---

## 6. Topic Modelling

Latent Dirichlet Allocation (**LDA**) was used to identify hidden discussion topics within customer reviews.

The topic modelling process involved:

- Creating a document-term matrix using `CountVectorizer`
- Training an LDA model with **5 topics**
- Assigning each review to its dominant topic
- Extracting the top keywords representing each topic

An interactive visualization was created using **pyLDAvis**, allowing exploration of topic relationships and keyword importance.

<p align="center">
  <a href="images/lda_visualization.png">
    <img src="images/lda_visualization.png" width="850">
  </a>
</p>

<p align="center">
<i>Figure 4. LDA topic visualization generated using pyLDAvis (click the image to enlarge).</i>
</p>

**Interactive Version**

If viewing this repository locally, you can explore the interactive topic model by opening:

- `images/lda_visualization.html`

---

# Project Results

The NLP pipeline generated several valuable business insights, including:

- Overall customer sentiment toward Luxury Beauty products
- Agreement between review sentiment and numerical ratings
- Frequently discussed product features and attributes
- Important named entities such as brands and organizations
- Hidden discussion topics extracted from thousands of customer reviews

These findings can support businesses by helping them:

- Improve product quality
- Monitor customer satisfaction
- Understand customer preferences
- Refine marketing strategies
- Make data-driven business decisions

---

# Project Structure

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

Through this project, I gained practical experience in:

- Building an end-to-end NLP pipeline
- Cleaning and preprocessing large-scale text datasets
- Performing sentiment analysis using TextBlob
- Applying Named Entity Recognition with SpaCy
- Discovering hidden topics using LDA topic modelling
- Visualizing NLP outputs using WordCloud, Matplotlib, and pyLDAvis
- Transforming unstructured customer reviews into actionable business insights

---

# Future Improvements

Potential future enhancements include:

- Applying transformer-based sentiment models (e.g., BERT or RoBERTa)
- Fine-tuning SpaCy's NER model for e-commerce-specific entities
- Performing aspect-based sentiment analysis
- Comparing multiple topic modelling approaches (LDA, NMF, BERTopic)
- Building an interactive dashboard using Streamlit or Dash

---

# Author

This project was completed as part of a Natural Language Processing (NLP) coursework assignment, demonstrating the practical application of modern NLP techniques to real-world Amazon customer review data.
