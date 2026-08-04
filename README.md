# Amazon Luxury Beauty Review NLP Analysis 🛍️✨

An end-to-end Natural Language Processing (NLP) pipeline designed to structure, process, and extract actionable business insights from Amazon customer product reviews within the **Luxury Beauty** category.

---

## 🚀 Project Overview
With millions of daily reviews flowing into e-commerce platforms like Amazon, manual analysis is virtually impossible. This project applies foundational and advanced NLP techniques to transform unstructured customer review text into structured insights—helping brands monitor sentiment, identify product features, recognize named entities, and uncover major latent themes.

---

## 🛠️ Tech Stack & Libraries
* **Language:** Python
* **Data Manipulation & Numerics:** `pandas`, `numpy`
* **Text Preprocessing & NLP:** `nltk` (Tokenization, Stopwords, Stemming, Lemmatization), `re`
* **Sentiment Analysis:** `TextBlob`
* **Named Entity Recognition (NER):** `spaCy` (`en_core_web_sm`)
* **Topic Modeling:** `scikit-learn` (CountVectorizer, Latent Dirichlet Allocation)
* **Visualization:** `matplotlib`, `seaborn`, `wordcloud`, `pyLDAvis`

---

## 📋 Key Steps & Implementation Workflow

### 1. Dataset Preparation (`Question 1b(i)`)
* **Dataset:** Amazon Review Data (Per-category dense subset: `Luxury_Beauty`).
* **Rationale:** Focusing on the Luxury Beauty category provides high business impact due to high-profit margins and the vital importance of maintaining brand prestige and consumer trust.
* **Action:** Loaded compressed JSON data via `gzip` and structured it into a clean Pandas DataFrame.

### 2. Vocabulary Building & Preprocessing (`Question 1b(ii)`)
Built a robust text-cleaning pipeline to prepare the `reviewText` column:
* Converted data types to string and transformed all text to **lowercase**.
* Removed raw noise, HTML tags, punctuation, and special characters using regular expressions (`[^a-zA-Z\s]`).
* Performed **tokenization**, removed English **stop words**, and applied **stemming** (`PorterStemmer`) and **lemmatization** (`WordNetLemmatizer`).
* **Visualization:** Generated a customized frequency-based **Word Cloud** highlighting prominent vocabulary terms like *skin, moisture, lotion, hair, product*.

### 3. Sentiment Analysis (`Question 1b(iii)`)
* **Method:** Applied `TextBlob` to calculate polarity scores ranging from `-1.0` (negative) to `+1.0` (positive) across the cleaned text.
* **Findings:** Plotted a sentiment distribution histogram showing a strong positive skew (concentrated between `0` and `0.6`), indicating general customer satisfaction.
* **Agreement Metric:** Evaluated the sentiment-rating agreement, confirming how polarity scores align with explicit user star ratings.

### 4. Named Entity Recognition - NER (`Question 1b(iv)`)
* **Method:** Utilized `spaCy`’s pre-trained statistical model (`en_core_web_sm`) to extract real-world entities (e.g., brands, product categories, quantities, locations).
* **Business Value:** Enables Amazon and third-party vendors to automatically map customer sentiments directly to specific product features, optimize targeted marketing, and prioritize product improvements.

### 5. Topic Modeling (`Question 1b(v)`)
* **Method:** Deployed **Latent Dirichlet Allocation (LDA)** via `scikit-learn` combined with `CountVectorizer`.
* **Execution:** Configured the model with $5$ latent topics using online learning updates.
* **Interpretation:** Extracted top keyword components per topic cluster (e.g., tracking skin-care and cosmetic application discussions) and visualized interactive topic clusters using `pyLDAvis`.

---

## 📊 Results & Business Takeaways
* **Operational Efficiency:** Automated categorization drastically reduces manual data auditing.
* **Sentiment Tracking:** Immediate identification of customer pain points helps resolve quality issues faster.
* **Targeted Strategies:** Topic modeling and NER empower marketing teams to allocate resources precisely toward high-demand product attributes.

---

## 📂 Repository Structure
```text
├── Luxury_Beauty_5.json.gz       # Raw dataset subset
├── notebook.ipynb                # Complete Google Colab / Jupyter Notebook
├── README.md                     # Project documentation
└── outputs/                      # Generated charts, word clouds, and visualizations
