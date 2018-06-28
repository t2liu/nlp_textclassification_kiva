# NLP Text Classification Project with Kiva.org Data

For this project I am using Multi-Class Text Classification to predict the Kiva Loan Sector using Kiva Loan Descriptions.

General outline/architecture structure of my project:

![project outline](https://github.com/t2liu/nlp_textclassification_kiva/blob/master/architecture_diagram.png)

### 1. Data:
This dataset is from the Kiva API (https://build.kiva.org). More specifically, this is Kiva’s Loans Data Snapshot, which contains all the loan listings that Kiva has posted from 2006 till January 2018. The dataset contains 1.4M rows and 34 columns. Each listing contains information that shows the key details of a loan, including name, loan amount, loan description, sector, etc.


loans.csv:

`|-- posted_time: the datetime the loan was posted on the Kiva.org website (datetime)
|-- original_description: the description of the loan in the language of the country the
borrower is from (string)
|-- translated_description: the description of the loan translated to English if the
original language is not English (string)
|-- sector: the specific category of the loan (categorical)`

### 2. Data Preprocessing:
Removing stop words, handle missing descriptions, handle imbalanced classes

### 3. Summarized Data:
(a) Visualization of the response variable
(b)

