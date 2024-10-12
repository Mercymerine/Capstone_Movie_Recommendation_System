

## Capstone Project: News Recommendation System

 
## Problem Statement

With the vast amount of news articles published daily, how can we efficiently recommend relevant news?

## Why Choose This System:

Enhanced Personalization: Unlike traditional news recommendation systems that rely heavily on user behavior data, our system focuses on the content itself, allowing for precise and personalized recommendations from the start.

 Real-Time Updates: By using RSS feeds, our system captures news articles as they are published, ensuring the most up-to-date information is available for recommendation.

Scalability: Capable of handling increasing volumes of data efficiently, making it suitable for growing and diverse news sources.

 Adaptability: Able to recommend new and niche articles without relying on popularity metrics, providing a balanced view of news.

## Data Sources and Data Acquisition

Using RSS (Really Simple Syndication)

## Why RSS?
Ease of Access: Provides structured content in XML/JSON format without complex parsing.

Efficiency: Delivers real-time updates as content is published, reducing the need for frequent polling.

Structured Data: Provides consistent data, making extraction easier without worrying about site layout changes.

No Authentication Required: Most RSS feeds are publicly accessible, without the need for authentication.

Automatic Updates: Users can subscribe to RSS feeds for automatic content updates.

Lower Legal Risk: Intended for public distribution, reducing legal concerns compared to web scraping.

## Methodologies Used

Content-Based Filtering

Advantages:

No Cold Start: Handles new/niche articles immediately.

Personalized from the Start: Uses article content for recommendations.

Scalable: Efficient as it grows with more news articles.

Advantages for News Recommendation:

No Need for User Data: Recommends based on article content, not user behavior.

Highly Relevant Recommendations: Driven by the similarity of the articles' content.

Personalization from Limited User Input: Personalized recommendations with minimal interaction.

Adaptable to New/Unpopular Items: Recommends new/niche articles without relying on popularity.

Scalability: Efficient with growing datasets, focused on article features.

## Preprocessing Steps Involved in NLP

Text Preprocessing Using spaCy

Sentence Segmentation

Tokenization

Lemmatization

Stemming

Named Entity Recognition (NER)

Lower Case Conversion

## Text Representation and Feature Engineering
Methods include: 
1. Bag of words: Simple, easy to implement bu it ignores word order and context
2. Word Embeddings (Word2Vec, GloVe): Captures semantic meaning and relationships
 but it is computationally intensive, complex to interpret
TF-IDF Vectorizer

Formula: $$\text{tf-idf}(t,d) = \text{tf}(t,d) \times \text{idf}(t)$$

Explanation:

tf (term frequency): How frequently a term appears in a document.

idf (inverse document frequency): Reduces the weight of terms that appear in many documents.

## Why TF-IDF?

Simplicity and Effectiveness: Balances term frequency and inverse document frequency, providing a more nuanced representation of text.

Reduces Overfitting: By reducing the impact of commonly occurring words, it helps prevent overfitting in the model.

Interpretability: Easier to understand and explain compared to more complex text representation methods like neural embeddings.

## Combining Headline and Text

List of Strings: Suitable for NLP because it maintains the integrity of individual text items, making processing more efficient.

Batch Processing: Preferred in NLP pipelines for transforming large datasets efficiently.

## Model Building Using Faiss

Faiss:

What it is: FAISS is a tool developed by Facebook AI Research (FAIR) to quickly find similar items in large collections of data. A library for efficient similarity search and clustering of dense vectors.

Why it’s used: Faster than cosine similarity, handles large datasets efficiently.

How it works:

Index: Structures the vectors for efficient querying.

Search: Finds the nearest vectors to a given query vector.

Parameters: Determines the number of neighbors to return and the precision of the search.

## Evaluation Metrics

## Precision:

Definition: The proportion of relevant results(recommended items) among all the retrieved results.
Formula: \[ \text{Precision} = \frac{\text{Number of relevant items retrieved}}{\text{Total number of items retrieved}} \]
If your recommendation system suggests 10 articles, and 7 of them are relevant to the user's query, your precision is 0.7 (70%).
Precision is important when you want to ensure that the items recommended are actually relevant to the user’s interests. High precision means fewer irrelevant results.

## Recall:

Definition: The proportion of relevant results retrieved compared to all relevant results.
Formula: \[ \text{Recall} = \frac{\text{Number of relevant items retrieved}}{\text{Total number of relevant items available}} \]
If there are 20 relevant articles in the entire dataset, and your system retrieves 10 of them, your recall is 0.5 (50%).
Recall is crucial when you want to capture as many relevant items as possible. High recall means that most of the relevant results are retrieved.
It calculates the number of relevant articles among the results and divides it by the total number of relevant articles available.

## F1 Score:

Definition: Harmonic mean of precision and recall.

Formula: $$\text{F1 Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$$

## Deployment

Using Streamlit for deployment

Easy, interactive web-based interface for users to interact with the recommendation system.

## Conclusion

Developed a news recommendation system using NLP and content based approach.

Data sourced from RSS feeds.

Deployed using Streamlit for user-friendly interaction.


