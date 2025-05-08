# Fake News Detection

## About
This is an certification purpose-oriented Data Science project of an international workshop - The Data Forge: Workshop and Contest, organized by NSDC-HerWILL Chapter Program. NSDC is the Northeast Big Data Innovation Hub’s National Student Data Corps (NSDC), part of Columbia University’s Data Science Institute.


## Overview
This project aims to give prediction about a news article - whether it is real or fake. It serves following aspects:

* Retrieving and accessing the target `.csv` file;
* Cleaning the data and preprocessing them;
* Training and testing the model;
* Predicting the type of news articles on the basis of trained model.


## Data Extraction
For this project, [this link](https://raw.githubusercontent.com/raima2001/HerWILL-NSDC-DS-Contest/main/news_dataset_subset%20(1).csv) was used, which contains 7,000 data pre-labeled with two word labels - real and fake. The dataset was accessed using `read_csv` function. The dataset has two (2) columns - `text` and `word_label`.


## Data Preprocessing
After successful data retrieval, preprocessing was performed using `nltk` library.

* `word_tokenize` function: Tokenizing the text
* `isalpha` function: Checking if a word is an alphabet or not
* `lower` function: Converting words to lowercase
* `stopwords` function (from `nltk.corpus` package): Getting a list of the stopwords (i.e., words that do not add any value to the text, e.g., a, an, the)
* `WordNetLemmatizer` function (from `nltk.stem` package): Getting the base word
* `PorterStemmer` function (from `nltk.stem` package): Reducing a word to its root form


## Data Training and Testing
Preprocessed data were split into 2 categories - training (first 5,000 data) and testing (last 2,000 data). `CountVectorizer` function from `sklearn.feature_extraction.text` package was used to convert the text into a matrix of token counts. `fit_transform` and `transform` functions were used on the training and testing data, respectively, to fit the model to the data and then transform the data into a matrix of token counts. Using `LabelBinarizer` function, training and testing labels were fit-transformed.


## Building the Model
Multinomial Naive Bayes (`MultinomialNB` function from `sklearn.naive_bayes` package) and Support Vector Machine (`SVC` function from `sklearn.svm` package) were used to build the model.


## Data Visualization
To visualize the word frequnecy for a specific word label, `WordCloud` function from the `wordcloud` package was used.

<table>
  <tr>
    <td align="center"><img src="https://github.com/ArnabUshna24/Fake-News-Detection/blob/main/real_news.png" alt="Real News" width="300"/></td>
  </tr>
  <tr>
    <td align="center"> Fig: Frequently used words having real news </td>   
  </tr>
</table>


## Model Accuracy
<table>
  <tr>
    <td align="left"> Multinomial Naive Bayes: 0.7905 </td>
    <td align="left"> Support Vector Machine: 0.5325 </td>
  </tr>
</table>


## Build from Source
Instructions are provided in the `ipynb` file.


If you have any queries, contact me: arnabnushna24@gmail.com
