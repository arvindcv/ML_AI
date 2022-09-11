> Written with [StackEdit](https://stackedit.io/).

# Objective
#### The objective of this Capstone project is to perform sentiment analysis of tweets. 
#### The effort is towards building a model which should be able to predict if a incoming tweet can be classified as a tweet which has sentiment towards indicating occurrence of disaster. e.g. I live on the pacific coast. a level 5 hurricane is heading towards our town.

## There are multiple uses of this project 
#### There are multiple uses of this effort 
#### 1. It can be used to proactively get hints of disasters before they can happen.
#### 2. It can be used by news agencies to know where possibly they need coverage.
#### 3. The model can be used for other sentiment analysis like customer support to know if there customer is happy or unhappy with their experience.
#### 4. The model can also be used for searching web to gather posts on a particular topic and weigh the sentiment across posts e.g. restaurants reviews, product reviews, company service reviews etc.

# Approach
###  The project attempts to build following models :-
#### 1. Model which uses Count Vectorizer and Stemmer along with Logistic Regression.
#### 2. Model which uses Count Vectorizer and Lemmetizer along with Logistic Regression.
#### 3. Model using Google Bert to predict the sentiment of tweets.

# Project Set up 
### Source Files
|Name|File/Directory|Details|
|--|--|--|
|[install.ipynb](https://github.com/arvindcv/ML_AI/blob/main/CapStone/install.ipynb "install.ipynb")  |File|1. Source file to install required packages for project|
|[function.ipynb](https://github.com/arvindcv/ML_AI/blob/main/CapStone/function.ipynb "function.ipynb")|File|1. Helper file which contains reusable function definitions|
|[TwitterFeed.ipynb](https://github.com/arvindcv/ML_AI/blob/main/CapStone/TwitterFeed.ipynb "TwitterFeed.ipynb")|File|1. File which has necessary logic to collect tweets for last 15 minutes|
|[TweetAnalysisUsingBert.ipynb](https://github.com/arvindcv/ML_AI/blob/main/CapStone/TweetAnalysisUsingBert.ipynb "TweetAnalysisUsingBert.ipynb")|File|1. File which has necessary logic to build model using Google Bert|
|[TweetAnalysisStemmer.ipynb](https://github.com/arvindcv/ML_AI/blob/main/CapStone/TweetAnalysisStemmer.ipynb "TweetAnalysisStemmer.ipynb")|File|1. File which has necessary logic to build model using Count Vectorizer, Stemmer and Logistic Regression|
|[TweetAnalysisLemmetizer.ipynb](https://github.com/arvindcv/ML_AI/blob/main/CapStone/TweetAnalysisLemmetizer.ipynb "TweetAnalysisLemmetizer.ipynb")|File|1. File which has necessary logic to build model using Count Vectorizer, Lemmetizer and Logistic Regression|
|[TweetAnalysisSpacy.ipynb](https://github.com/arvindcv/ML_AI/blob/main/CapStone/TweetAnalysisSpacy.ipynb "TweetAnalysisSpacy.ipynb")|File|1. File which has necessary logic to build model using Spacy|
|[data](https://github.com/arvindcv/ML_AI/tree/main/CapStone/data "data")|Directory|1. Data folder which contains the input data for building the Logistic Regression Model and input data for building model with Google Bert|
|[train.csv](https://github.com/arvindcv/ML_AI/blob/main/CapStone/data/train.csv "train.csv")|File|Tweet data of 10,000 tweets that has been used to build the model with Logistic Regression|
|[train](https://github.com/arvindcv/ML_AI/tree/main/CapStone/data/train "train")|Directory|Directory which contains input data to train the Google Bert model. The folder structure that Google Bert follows is to have multiple files for each of the class being predicted|
|[pos](https://github.com/arvindcv/ML_AI/tree/main/CapStone/data/train/pos "pos")|Directory|contains all the positive tweets which reflect a disaster event in it from the sample data. Each tweet is present in a file of its own for Google Bert to train|
|[neg](https://github.com/arvindcv/ML_AI/tree/main/CapStone/data/train/neg "neg")|Directory|contains all the negative tweets which reflect there are no disaster events in it from the sample data. Each tweet is present in a file of its own for Google Bert to train|

# Analysis and Finding
#### 1. Logistic Regression has been considered as it has proven to be performing better along with Count Vectorizer for NLP classification problems.
#### 2. Between Stemmer and Lemmetizer, the combination of Lemmetizer with Count Vectorizer and Logistic Regression has shown to produce the best accuracy amongst other models.
#### 3. Accuracy of the model on raw tweet data has been observed to be 0.79
#### 4. Class imbalance has been observed with negatives being more in the available sample hence SMOTE has been used to over sample the data to balance the class.
#### 5. Accuracy of the model on balanced class shot up to 0.9748 after balancing the class.
#### 6. Accuracy of the model after applying gridsearchCV has been best at 0.9961
#### 7. Google Bert has been trained and an accuracy of 0.9998 has been observed with it.
#### 8. Hyper parameters used for tuning - 
		max_iter=[1,10,1000]
		solvers = ['newton-cg', 'lbfgs', 'liblinear']
		penalty = ['l2']
		c_values = [100, 10, 1.0, 0.1, 0.01]
#### 9. GridSearchCV has been the most accurate model and the slowest one w.r.t fitting time.

Metrics of Lemmetizer model
| model | best_score |best_time|accuracy_score|roc_auc_score|
|--|--|--|--|--|
|Count Vectorizer and Logistic Regression Lemmetizer[Raw data]|0.799037|0.985237|0.799037|0.785093|
|Count Vectorizer and Logistic Regression Lemmetizer [Balanced Data]|0.974868|1.744217|0.974868|0.974868|
|Count Vectorizer and Logistic Regression Lemmetizer [CV]|0.996197|69.286025|0.996197|0.996197|

# Prediction  Output

### Lemmetizer prediction --
![Lemmetizer Prediction](/Users/achandrasekhar/Desktop/Lemmetizer_Output.png)

### Stemmer prediction --
![Stemmer Prediction](/Users/achandrasekhar/Desktop/Stemmer_Output.png)

### Bert prediction --
![Bert Prediction](/Users/achandrasekhar/Desktop/Bert_Output.png)

### Spacy prediction --
![Spacy Prediction](/Users/achandrasekhar/Desktop/Spacy_Output.png)


