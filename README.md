# 💄 Amazon Luxury Beauty Reviews - Natural Language Processing (NLP) Analysis

An end-to-end Natural Language Processing (NLP) project analysing over 22,000 Amazon Luxury Beauty customer reviews. The project transforms unstructured review text into business insights through text preprocessing, sentiment analysis, Named Entity Recognition (NER), and topic modelling.

---

## 🚀 Project Overview

Customer reviews contain valuable information about product quality, customer satisfaction, and purchasing behaviour. This project applies multiple NLP techniques to discover patterns hidden within Amazon Luxury Beauty reviews and answer questions such as:

- What overall sentiment do customers express?
- Which words and product features appear most frequently?
- Which brands, products, and entities are commonly mentioned?
- What major discussion topics emerge from thousands of customer reviews?

The analysis demonstrates how NLP techniques can convert raw text into actionable business intelligence.

---

## 📂 Dataset

**Source:** Amazon Review Dataset (UCSD)

https://cseweb.ucsd.edu/~jmcauley/datasets/amazon_v2/

**Dataset Used**

- Luxury_Beauty_5.json.gz
- Amazon Luxury Beauty Reviews
- Review period: **May 1996 – October 2018**

---

## 🛠️ Tech Stack & Libraries

**Language**

- Python

**Key Libraries**

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

The project follows a complete NLP workflow:

1. Load the Amazon review dataset into a Pandas DataFrame.
2. Clean and preprocess review text.
3. Build a vocabulary from processed reviews.
4. Generate a WordCloud of the most frequent terms.
5. Perform sentiment analysis using TextBlob.
6. Extract named entities using SpaCy.
7. Discover hidden discussion topics using LDA topic modelling.
8. Produce business insights from the analysis.

---

# 📈 Key Findings & Visualizations

## 1. Vocabulary Analysis

Reviews were cleaned through:

- Lowercasing
- Removal of punctuation and special characters
- Tokenization
- Stopword removal
- Stemming
- Lemmatization

A WordCloud highlights the vocabulary most frequently appearing across Luxury Beauty reviews, providing an intuitive overview of customer discussions.

[📷 View Full Resolution WordCloud](images/wordcloud.png)

![WordCloud](images/wordcloud.png)

---

## 2. Sentiment Analysis

Sentiment polarity was calculated using **TextBlob**, assigning each review a score between **-1** and **+1**.

Key observations include:

- Majority of reviews exhibit positive sentiment.
- Negative reviews form a much smaller proportion.
- Textual sentiment generally aligns with customer star ratings.

[📷 View Sentiment Distribution](images/sentiment_histogram.png)

![Sentiment Histogram](images/sentiment_histogram.png)

---

## 3. Named Entity Recognition (NER)

Named Entity Recognition was performed using SpaCy's pretrained English model (`en_core_web_sm`).

Entities extracted include:

- Products
- Organizations
- Locations
- People
- Dates
- Quantities
- Monetary values

NER converts free-text reviews into structured information that businesses can analyse more efficiently.

[📷 View NER Visualization](images/ner_visualization.png)

![NER](images/ner_visualization.png)

---

## 4. Topic Modelling

Latent Dirichlet Allocation (LDA) was applied to discover hidden themes across customer reviews.

The workflow included:

- CountVectorizer
- Document-Term Matrix construction
- Five-topic LDA model
- Topic assignment for every review
- Keyword extraction

The resulting pyLDAvis visualization illustrates topic separation and the importance of keywords within each discovered topic.

[📷 View LDA Visualization](images/lda_visualization.png)

![LDA](images/lda_visualization.png)

Interactive version:

**images/lda_visualization.html**

---

# 💡 Business Insights

The analysis demonstrates how NLP techniques can support data-driven decision making by helping businesses:

- Monitor customer satisfaction
- Identify common product strengths and weaknesses
- Understand recurring customer concerns
- Detect frequently mentioned brands and products
- Discover emerging customer discussion topics
- Support product development and marketing strategies

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

## 🚀 Future Improvements

Potential extensions include:

- BERT or RoBERTa sentiment models
- Aspect-based sentiment analysis
- BERTopic and NMF topic modelling
- Fine-tuned SpaCy NER models
- Interactive Streamlit dashboard

---

## 👤 Author

This project was completed as part of a Natural Language Processing (NLP) coursework assignment, demonstrating practical NLP techniques on real-world Amazon customer review data.
