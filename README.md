this is the context, 

TABLE OF CONTENTS

Question 1 
The assessment is to assess your ability to design NLP solutions based on the following case. 
Amazon is one of the world's largest e-commerce companies, with a vast product range. It receives hundreds of thousands of product reviews daily from its users worldwide. These reviews contain valuable information about the product and customer sentiments towards it. 
However, with the volume of incoming data, it's nearly impossible for Amazon to manually analyse all the reviews to extract actionable insights. This is where NLP comes in. Your task is to create an NLP solution to help Amazon structure and analyse the review data. 
Here is an Amazon review dataset collected in the range of May 1996 - Oct 2018, including reviews (ratings, text, helpfulness votes), product metadata (descriptions, category information, price, brand, and image features), and links (also viewed/also bought graphs). 
You are encouraged to use the smaller per-category dense subsets, which have been reduced to extract the k-core, such that each of the remaining users and items have k reviews each.

Dataset link: https://cseweb.ucsd.edu/~jmcauley/datasets/amazon_v2/

Question 1a 
Based on your task, which is to create an NLP solution to help Amazon structure and analyse the review data, determine a scenario/problem that you are going to analyse and design NLP solution for the identified scenario/problem. (word limit: 500) 
(20 marks) 

Question 1b 
Design and implement relevant NLP analysis flow to address the identified questions, which includes but is not limited to: 
(i) Dataset preparation; (ii) Vocabulary building; (iii) Sentiment analysis; (iv) Named Entity Recognition; (v) Topic modeling

Question 1b(i) 
Dataset preparation: Select one of the smaller per-category dense subsets, optionally filter some data points (at least 2000 reviews) from the selected sub-dataset to prepare a new sub-dataset to be used in this assessment. For example, you are free to filter by product, by user etc. 
Explain the rationale behind the choice. Export the subset as a .csv or .json file. (word limit: 300) 
Note: Discuss with your instructor of your filter choice before you start working on this project. 
(12 marks)




Question 1b(ii) 
Vocabulary building: Construct a vocabulary from customers’ review data, interpret what each step does and why is it important for subsequent NLP tasks, and finally generate a word cloud image for better visualization of the vocabulary. (word limit: 500) 
(15 marks)

Question 1b(iii) 
Sentiment analysis: Evaluate sentiment analysis on the review texts, visualize the distribution of sentiment, conclude the challenges and viable solutions to address these challenges in sentiment analysis for e-commerce platforms based on your findings (e.g., evaluate whether the sentimental findings are in agreement with their ratings). (word limit: 400) 
(18 marks)

Question 1b(iv) 
Named Entity Recognition (NER): Demonstrate the application of NER in review analysis, investigate the importance of NER in extracting key information for review analysis, select examples of entities that are relevant in an e-commerce setting and explain how businesses can benefit from NER. (word limit: 500) 
(15 marks)

Question 1b(v) 
Topic modeling: Assess topic modeling techniques on the sub-dataset you selected and evaluate how business can use topic modeling to categorize and understand the major themes within customer reviews. (word limit: 500) 
(15 marks)

Question 1c 
Reflect on the journey of your study in this course, describe one problem/challenge that you faced, and how you managed to solve the problem. (word limit: 300) 
(5 marks)























Question1a

Amazon is one of the largest and most influential companies in the world. Being known as one of the earliest e-commerce online platform for books, it has now expanded to selling almost any and all products available in the world that is legal. As such, it would make sense to discover out of all the products that are being sold, how the organization can further optimize its operations and increase sales. 

With the sheer size of volume of incoming data, it will be impossible for Amazon to manually analyse and extract insight. This is where I come in. My job will be to use NLP to analyse the reviews data and create actionable recommendations. 

To begin, I would first build the vocabulary for the NLP model. This involves data pre-processing, then tokenizing the text in the ‘reviewText’ column into individual words or n-grams., and building a dictionary mapping each unique to an integer index so that machine learning algorithms can be applied.

Next, I will proceed to perform sentiment analysis. I will find out if the reviews are positive, negative or neutral. In order to do that, I will use TextBlob, a pre-trained model in python. This library provides simple but powerful NLP has a built in sentiment analyzer that is pre-trained on dataset.

After sentiment analysis, I will move on to named entity recognition. Extracting named entities like product names, brands, features, provide insightful structure data from unstructured text. I will proceed to use a pretrained NER model called SpaCy and apply it on the reviews column. This will allow me to extract entities and analyze questions such as which brands are mentioned most often, and what attributes are frequently discussed.

Lastly, I will apply topic modelling to understand the main topics and themes across the reviews. I will use a unsupervised learning technique, called LDA (Latent Dirichlet Allocation). First, I will chose the number of clusters(topics k) to extract. Next, I will run the LDA model to get the topic-word and document-topic distributions. By examining the most relevant terms for each topic, I will give them informative labels. Lastly, I will analysis the distribution of topics across the corpus, such as which topics are most prevalent, what are the main themes of each topics.

To summarise, these techniques such as sentiment analysis, NER and topic modelling can help Amazon provide valuable insights such as overall customer sentiments towards each product/category and trends over time, most popular and discussed brands and features, common themes and topics mentioned in reviews. These information can be used to improve products, adjust marketing and branding, guide business decision and enhance customer experience, ultimately increasing sales.


Question1b(i)

Given the enormous volume of sales data, I will have to filter and focus on a particular category. My goal is to improve the sales and bring in more revenue. I will choose to focus on the “Luxury Beauty” category as these are items with significantly higher margins. Also, one of the major selling point of luxury beauty items is its prestige and brand image. 

Hence, it would make a lot of sense of me to analyse the review sentiments for luxury beauty items. First, I can monitor brand image and make adjustment for sales strategy. Secondly, my work will have much greater impact on the organisation as compared to improving the sales of books, despite it being amazon’s original product category. 

Showing stakeholders’ how NLP can make significant impact to the organisation is extremely vital as it can prove to them that new technology is useful and essential. This will make onboarding new technology in the future much easier as I am able to prove its effectiveness. If I have conducted NLP on the ‘books’ category, it might raise questions and objections as computing cost and other resources such as time are incurred, and they cannot justify the small increase in revenue from more books being sold. This will increase resistance in bringing in new technical technology in the future, which will hinder innovation.




Question1b(ii)

I will first create a pipeline to do data pre-processing, this is an important step as the text from “reviewText’ column from the luxury beauty dataset are not in the optimal format for the NLP techniques that we are going to use later.

In the pipeline, we will need to create the functions that will help us clean up the reviews text from the Luxury Beauty dataset. The purpose of this step is to:

1.  1)    Convert all the objects in the column into string data type. 

1.  2)    Standardizing text: by concerting all characters to lowercase, this will ensure that the same word in various forms is recognized as a single word regardless of their different spellings, such as “APPLE”, “Apple” or “apple”. The word would be treated as the same word. Part of this step would be to also include the removal of white spaces.

1.  3)    Remove raw noise: Text often contain text/symbols that are irrelevant to the analysis such as HTML, emojis, special Characters and punctuation.

1.  4)    Removing all characters except letters (a-z, A-Z)from each string in the text, keeping only the regular expression pattern a-zA-Z. With all the steps up to so far, it will be less computationally expensive to proceed to the next step.

1.  5)    I tend move on tokenize the text, before further processing with stemming the text, and then lastly lemmatize the text. With that, the pre-process is done and I can proceed on to use NLP techniques. It is important to tokenize first before stemming and lemmatizing are done.










Finally, I will generate a word cloud image for better visualization of the vocabulary. What this does is that regardless of their sentiments, the word cloud can show us what the vocabulary contains and identify the most frequently appearing words. From analysing the text in Luxury Beauty, I can observe terms such as ‘product’, ‘skin’, ‘moisture’, ‘lotion’ and ‘hair’ are prevalent. These words are consistent with the typical language used in luxury beauty products, where things like makeup, lotion, hair products are often sold, hence indicating their relevance within this subset.






















Question1b(iii)

Next, for the sentiment analysis. Since I have already pre-processed the text in review column, I can now apply NLP technique to it. I will be using a supervised learning method for classification. 

I will be using TextBlob, a python library that provides simple API for performing sentiment analysis. Since TextBlob internally handle text preprocessing and representation, I do not need to explicitly vectorize the tokens

After I pass through the text in ‘reviewText’ column, I will be able to get the polarity score for each row of the text in the column. The polarity score ranges from -1.00, negative sentiment, to 1.00, positive sentiment. And 0 is neutral sentiment.  

In order to visualize the overall trend of sentiment in the luxury beauty dataset, I will then plot the polarity values in a histogram to show the distribution of the sentiment from negative to positive. The results show that most reviews are concentrated between 0 to 0.6. This means that overall, customers are happy and satisfied to a small extent. 








"Sentiment-Rating Agreement" value is 0.64, which suggests a moderate to strong agreement between sentiment and ratings. It indicates that, on average, reviews with positive sentiment have ratings that are 0.64 points higher than reviews with negative sentiment.
This insight can be valuable for understanding the relationship between the sentiment expressed in the text and the overall satisfaction or opinion of users as reflected in their ratings. It can help identify if there is a consistent alignment between the sentiment analysis results and the user-provided ratings, which can be useful for validating the sentiment analysis model or identifying discrepancies that may require further investigation.







Question1b(iv)

In order to perform Named Entity Recognition, I will first have to install SpaCy, a pre-trained statistical model that can identify and extract named entities from text. Named entities are real-world objects such as persons, organizations, locations, dates, quantities, monetary values, percentages, and more. 

Next, I will install the English language model as the text in “reviewText” column is in English.

The application of NER in this review analysis can help automatically identity and categorizing entities, which can includes product name, brands, features, location and more. By extracting these entities, amazon can gain a deeper understanding of customer sentiments, preferences, locations and concerns.

Sentiment analysis: By associating entities with sentiment scores, amazon can find out the overall sentiment towards certain brands, products, or features mentioned in the reviews.

Product improvement: Identifying frequently mentioned product features or issues in review can allow amazon to focus and prioritize on those areas and quickly address customer concerns.
Customer segmentation: By analysing customers from different geographically locations, amazon can identity different customer segments with different specific preferences or needs, allowing targeted marketing, which can save marketing dollars.





To sum up, it is a valuable tool for amazon, which have massive incoming sales data coming in every single day. By automatically identifying and categorizing relevant entities, amazon can gain insights into customer sentiments, preferences and concerns. After that, Amazon can proceed to make data-driven decisions, improve their products, and enhance customer satisfaction.

 

Question1b(v)

For topic modelling, I will be using the Latent Dirichlet Allocation (LDA) model on the review text. LDA is a widely used probabilistic topic modelling algorithm that discovers latent topics within a collection of documents. It assumes that each document is a mixture of topics, and each topic is a distribution over words. By applying LDA to the "reviewText" column, amzon can uncover the main themes customers discuss in their luxury beauty product reviews.

Taking account that it is an unsupervised machine learning technique, I will have to specific the number of clusters to 5, and then make adjustments accordingly when I see the results. Having too many topics/clusters may not be a good idea as the groupings are not meaningful.

To interpret the results, the LDA returns the specified set of clusters, each represented by a distribution of words. Amazon can the look at the top words associated with each cluster to understand the main theme in the reviews discussion

For instance, looking at the second largest cluster, ‘2’, we can see that most customers are talking about themes such as ‘skin’, ‘face’, ‘moistur’ and ‘feel’. With this knowledge, amazon can identify the frequently aspects that the customers care about in the luxury beauty category.




Also, amazon can further analyse other topic distribution and find out how the topic distribution of words vary across each topic varies across different clusters. Then, amazon can leverage with the insights by identify and enhancing product features and benefits. They can also know with a high certainty where their marketing dollars should be allocated to target specific market segments and communicate better, leading to an even higher positive sentiment analysis. 

Question1c

At the start of the course, my biggest concern was my basic python knowledge. Knowing only a few key concepts like numpy, pandas and seaborne, I wondered if I was able to finish the course as the codes look so daunting and foreign. When I looked through the codes for demo 1, I realised that I could not read them at all. To make matters worse, I was in a class with others who seem to know what they are doing, with some with quite high python knowledge.
Looking back, my concerns were actually not very valid as the key to NLP is understanding the entire process. Knowing what the entire NLP pipeline is like, knowing what my NLP end goals are, what are the steps to take in order to execute and get the intended goals really helped.
When I finally understood how doing step 1 will lead to step 2, then leading to step 3, then finally arriving at the stage where I can implement the task (sentiment analysis for instance), I realised that the codes are not difficult at all. The codes are just tools to help me get from one point to another, understanding the underlying logic of the steps finally made me able to read the codes smoothly.

and these are the codes,

import numpy as np
import pandas as pd


def parse(path):
  g = gzip.open(path, 'r')
  for l in g:
    yield json.loads(l)

import gzip
import json

def parse(path):
  g = gzip.open(path, 'rb')
  for l in g:
    yield json.loads(l)

def getDF(path):
  i = 0
  df = {}
  for d in parse(path):
    df[i] = d
    i += 1
  return pd.DataFrame.from_dict(df, orient='index')

df = getDF('Luxury_Beauty_5.json.gz')


df.info()


df.shape


df.head()


import nltk
from nltk.tokenize import word_tokenize
from nltk.corpus import stopwords
from nltk.stem import WordNetLemmatizer, PorterStemmer
import re

nltk.download('punkt')
nltk.download('stopwords')
nltk.download('wordnet')

def preprocess_text(text):
    # Convert objects to strings
    text = text.astype(str)
    
    # Convert to lowercase
    text = text.apply(lambda x: x.lower())
    
    # Remove whitespace
    text = text.apply(lambda x: x.strip())
    
    # Keep only regular expression a-zA-Z
    text = text.apply(lambda x: re.sub(r'[^a-zA-Z\s]', '', x))
    
    # Tokenize the text
    text = text.apply(lambda x: word_tokenize(x))
    
    # Remove stopwords
    stop_words = set(stopwords.words('english'))
    text = text.apply(lambda x: [word for word in x if word not in stop_words])
    
    # Stem the words
    stemmer = PorterStemmer()
    text = text.apply(lambda x: [stemmer.stem(word) for word in x])
    
    # Lemmatize the words
    lemmatizer = WordNetLemmatizer()
    text = text.apply(lambda x: [lemmatizer.lemmatize(word) for word in x])
    
    return text

df['clean_text'] = preprocess_text(df['reviewText'])
print(df.head())



import seaborn as sns
import matplotlib.pyplot as plt

from wordcloud import WordCloud
import matplotlib.pyplot as plt

text = ' '.join(df['clean_text'].apply(lambda x: ' '.join(x)))

wordcloud = WordCloud(width=800, height=400, background_color='white').generate(text)

plt.figure(figsize=(10, 5))
plt.imshow(wordcloud, interpolation='bilinear')
plt.axis('off')
plt.tight_layout()
plt.show()



!pip install nltk textblob
import nltk
from textblob import TextBlob
import matplotlib.pyplot as plt



def get_sentiment(text):
    blob = TextBlob(' '.join(text))
    sentiment = blob.sentiment.polarity
    return sentiment

df['sentiment'] = df['clean_text'].apply(get_sentiment)



plt.figure(figsize=(8, 6))
plt.hist(df['sentiment'], bins=20, range=(-1, 1), alpha=0.8, color='skyblue', edgecolor='black')
plt.xlabel('Sentiment Polarity')
plt.ylabel('Frequency')
plt.title('Distribution of Sentiment')
plt.show()




df['rating'] = df['overall']
df['sentiment_category'] = df['sentiment'].apply(lambda x: 'Positive' if x > 0 else ('Negative' if x < 0 else 'Neutral'))

sentiment_rating_agreement = df[df['sentiment_category'] == 'Positive']['rating'].mean() - df[df['sentiment_category'] == 'Negative']['rating'].mean()
print(f"Sentiment-Rating Agreement: {sentiment_rating_agreement:.2f}")



!pip install spacy

!python -m spacy download en_core_web_sm


import spacy
from spacy import displacy
import re

# Load the SpaCy English model
nlp = spacy.load("en_core_web_sm")

def preprocess_text(text):
    # Convert to string if not already
    text = str(text)
    # Remove HTML tags and URLs
    text = re.sub(r'<[^>]*>|http\S+', '', text)
    # Remove extra whitespaces
    text = re.sub(r'\s+', ' ', text).strip()
    return text

def tokenize_text(text):
    # Tokenize the text using SpaCy
    doc = nlp(text)
    # Return the tokenized text as a string
    return " ".join([token.text for token in doc])

def perform_ner(text):
    # Process the text with SpaCy
    doc = nlp(text)
    # Extract named entities
    entities = [(ent.text, ent.label_) for ent in doc.ents]
    return doc, entities

# Select a subset of 10,000 rows from the dataframe
subset_df = df.head(10000)

# Apply text preprocessing to the 'reviewText' column
subset_df['preprocessed_text'] = subset_df['reviewText'].apply(preprocess_text)

# Tokenize the preprocessed text
subset_df['tokenized_text'] = subset_df['preprocessed_text'].apply(tokenize_text)





import spacy

# Load the SpaCy English model
nlp = spacy.load("en_core_web_sm")

# Iterate over each row in the 'preprocessed_text' column and perform NER
for text in subset_df['preprocessed_text']:
    doc = nlp(text)
    for ent in doc.ents:
        print(f"Entity: {ent.text}, type: {ent.label_}")


import spacy
from spacy import displacy

# Load the SpaCy English model
nlp = spacy.load("en_core_web_sm")

# Assuming you have already created the subset_df dataframe with the 'preprocessed_text' column
# subset_df = df.head(10000)

# Iterate over each row in the 'preprocessed_text' column and perform NER
for text in subset_df['preprocessed_text']:
    doc = nlp(text)
    
    # Render the visualization for each text
    displacy.render(doc, style="ent", jupyter=True)




import spacy
from spacy import displacy

# Load the SpaCy English model
nlp = spacy.load("en_core_web_sm")

# Assuming you have already created the subset_df dataframe with the 'preprocessed_text' column
# subset_df = df.head(10000)

# Iterate over each row in the 'preprocessed_text' column and perform NER
for text in subset_df['preprocessed_text']:
    doc = nlp(text)
    
    # Render the visualization for each text
    displacy.render(doc, style="ent", jupyter=True)



from sklearn.feature_extraction.text import CountVectorizer
from sklearn.decomposition import LatentDirichletAllocation
import numpy as np

vectorizer = CountVectorizer()
vectorizer.fit(text_prep)
text_matrix = vectorizer.transform(text_prep)
print("text matrix shape:", text_matrix.shape)




term_count = np.sum(text_matrix, axis=0)
term_count = term_count.A1 # convert to 1d array

sorted_idx = np.argsort(-term_count) # argsort sorts in ascending order. add minus to sort in descending order
term_count = term_count[sorted_idx]
term = vectorizer.get_feature_names_out()[sorted_idx]

for i in range(0, 10):
    print(f"{term[i]}: {term_count[i]} times")



n_topics = 5 
# learning_method: Method used to update _component. Only used in fit method. 
# In general, if the data size is large, the online update will be much faster than the batch update.

lda_model = LatentDirichletAllocation(n_components=n_topics, learning_method="online",
                                      random_state=0, verbose=1, max_iter=50)

# # if we target to have 4 topics, we can use less iterations
# n_topics = 4 
# lda_model = LatentDirichletAllocation(n_components=n_topics, learning_method="online",
#                                       random_state=0, verbose=1, max_iter=10)

lda_topic_matrix = lda_model.fit_transform(text_matrix)


print(lda_topic_matrix.shape)



i = 0
print(f"Doc {i}: {text_prep[i]}")
print(f"Topic probability of Doc {i}: {lda_topic_matrix[i]}, which means")
for k in range(n_topics):
    print(f"Doc {i} has a probability of {lda_topic_matrix[i,k]} belonging to topic {k}")
print(f"The sum of all probs: {lda_topic_matrix[i].sum()}")


topic = np.argmax(lda_topic_matrix[i])
print(topic)


for i in range(0, 10):
    topic = np.argmax(lda_topic_matrix[i])
    print(f"Document {i} belongs to topic {topic}")



df["topic"] = np.argmax(lda_topic_matrix, axis=1)
print(df[["topic", "clean_text"]])



top_n_components = 30
for i in range(n_topics):
    print(f"\nTopic {i} top {30} components")
    weight = lda_model.components_[i]
    sorted_idx = np.argsort(-weight) # sort in descending order of component weights
    sorted_idx = sorted_idx[0:top_n_components]
    weight = weight[sorted_idx]
    word = vectorizer.get_feature_names_out()[sorted_idx]
    print(word)
    #print(weight)



!pip install pyLDAvis
import pyLDAvis
import pyLDAvis.lda_model
pyLDAvis.enable_notebook()
lda_display = pyLDAvis.lda_model.prepare(lda_model, text_matrix, vectorizer)
lda_display


write up for me nicely a summary of what i have done for my github page on the readme.md file. write it so that i can just copy and paste over. 
