# NLP Text Classification Project with Kiva.org Data

For this project I am using Multi-Class Text Classification to predict the Kiva Loan Sector using Kiva Loan Descriptions.


**NOTE:** Since the dataset is too big to put on my repo, please follow the following link to retrieve the dataset and files needed to run the Jupyter notebook:

Main Dataset:
[loans.csv](http://s3.kiva.org/snapshots/kiva_ds_csv.zip)

Word Embeddings (if decided to run the CNN part of my notebook)
[pre-trained wiki news word embeddings (300D)](https://s3-us-west-1.amazonaws.com/fasttext-vectors/wiki-news-300d-1M.vec.zip)

General outline/architecture structure of my project:

![project outline](https://github.com/t2liu/nlp_textclassification_kiva/blob/master/architecture_diagram.png)

### 1. Data:
This dataset is from the Kiva API (https://build.kiva.org). More specifically, this is Kiva’s Loans Data Snapshot, which contains all the loan listings that Kiva has posted from 2006 till January 2018. The dataset contains 1.4M rows and 34 columns. Each listing contains information that shows the key details of a loan, including name, loan amount, loan description, sector, etc.


loans.csv:

`|-- posted_time: the datetime the loan was posted on the Kiva.org website (datetime)`

`|-- original_description: the description of the loan in the language of the country the
borrower is from (string)`

`|-- translated_description: the description of the loan translated to English if the
original language is not English (string)`

`|-- sector: the specific category of the loan (categorical)`

### 2. Data Preprocessing:
Removing stop words, handle missing descriptions, handle imbalanced classes

### 3. Summarized Data:
(a) Visualization of the response variable

(b) To understand more about the data, a tf-idf vector is calculated for each of the loan descriptions.


**TF-IDF**

Calculate a tf-idf vector for each of loan description:

- sublinear_df is set to True to use a logarithmic form for frequency.
- min_df is the minimum numbers of documents a word must be present in to be kept. 
- norm is set to l2, to ensure all our feature vectors have a euclidian norm of 1.
- ngram_range is set to (1, 3) to indicate that we want to consider unigrams, bigrams, and tri-grams.
- stop_words is set to "english" to remove all common pronouns ("a", "the", ...) to reduce the number of noisy features.


Then using the tf-idf vectors, the loan description terms that are the most correlated with each of the sectors will be listed.

### 4. Fit Models:
- Multi-Class Naive Bayes Classifier

		(1) TF-IDF Vectorizer as features

		(2) Count Vectorizer as features

- Attempted: CNN
