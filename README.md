# Tweet_Sentiment_Analysis  
Sentiment analysis is the automated process of analyzing text data and classify it into sentiments positive, negative, or neutral. Twitter is a microblogging site in which users can post updates (tweets) to friends (followers). 
It has become an immense dataset for sentiment analysis. This approach is useful for consumers who can use sentiment analysis to search for products, for companies that aim at monitoring the public sentiment of their brands, and for many other applications. 

## Data Processing  
The dataset I used is “Sentiment140”, which originated from Stanford University and has 1600000 tweets. This dataset contains information such as 'label', 'time', 'user_name', 'text', I only keep 'text' and 'label' for later analysis and modeling.
Since the raw data includes a large amount of noise like punctuation, stop words (such as 'the', 'in', 'for'). Thus, I have following steps for pre-processing:  
1) Removing Twitter Handles (@user);  
2) Removing Punctuations, Numbers, and Special Characters;  
3) Remove short words;  
4) Tokenization;  
5) Stemming;  
6) Removing stopwords;

## Feature Extraction  
We need to convert textual data to numerical representation for model training. In this project, I firsrly tried the most basic approach: Bag-Of-Word (BOW). After applyin **Count vectorizer**, each tweet is represented as numerical vectors based on the vocabulary built from the corpora.
This feature counts the appearance of the words in each text based on corpus.  **Tfidf vectorizer** can generate another type of vector value which is the product of TF (Term Frequencey) and IDF (Inverse Document Frequency) that takes informativeness of terms into consideration.  
**N-grams** is a natural extension of BOW/TF-IDF which retain some context by breaking long text into sequences of words. An n-gram is simply any sequence of n tokens (words). In this work, I evaluated some common n-grams: 1-grams, 2-grams and 3-grams, and also checked the test accuracy for a different number of features (size of vocabulary).


## Modeling  
After fixing the optimal feature sets and the number of features, I tried 2 different models: Logistic Regression and Naive Bayes Model.
