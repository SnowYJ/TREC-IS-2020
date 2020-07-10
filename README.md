
## Classification of tweets for aiding crisis and disaster management.

### TREC-IS 2019 overview:

* Dataset includes two labels. One is 'categories' label involving 25 information type, which is a multi-label classification task. Another is 'priority' label that includes four categories. It is a multi-class classification task.

<img src="image/dataset.png" width="800">

* Metrics: F1-score and accuracy for actionable and all information type in multi-label task. RMSE for actionable and all information type in multi-class task.
* 6% participants use word embedding.
* Deep learning is increasing popular from 29% to 39%. However, classic machine learning is more effective.
* **No participants use link information!** "it seems likely that usage of such data is still largely unexplored for this task."
* System Performance:
<image src="image/overview.png" width="800">

### Eight Participants Notebook:
* CNN
* SIF sentence embeddings, pre-trained sentence embeddings, BERT word embeddings + DNN
* Data enhancement + glove.840B.300d + bi-lstm + NN
* TF-IDF + k-nearest neighbors.
* Feature engineering + GBT, Random Forest and linear regression.
* Data augmentation (GPT-2, smote) + bi-LSTM variants.

### Future Advice:

<img src="image/future.png" width="600">

Reference:
[TREC-IS Dataset](http://dcs.gla.ac.uk/~richardm/TREC_IS/2020/data.html),
[2019 TREC-IS overview](http://dcs.gla.ac.uk/~richardm/TREC_IS/2020/ISCRAM_2020_TREC_IS.pdf)

****
<img src="image/system.png" width="800">

### Improvement Plan:

1. **Feature engineering:** manually construct dataset instead of word embedding.
>* NER feature: number of location, person, organization mentioned in tweets.
>* Social feature: number of friends, followers, retweet.
>* Morphological features: number of words, upper case words, emoji, hashtags and URLs.
>* Sentiment features: number of positive and negative words. 

<img src="image/feature_importance_1.png" width="600">

2. **Use ensemble learning:**

3. **Use link in tweets:** focus on 'critical' labeled tweets.

### My Project:
* system_0: dataset processing (data cleaning, feature engineering and data augmentation EDA)
* system_1: TFIDF Logistic Regression (multi-class & multi-label)
* system_2: bi-GRU and glove (multi-class)
* system_3: bi-GRU and glove (multi-label)
* system_4: fine-tuning Bert (multi-class)
* system_5: fine-tuning Bert (multi-label)

### Result:

| Group | Actionable F1 | All F1 | All Accuracy | Actionable RMSE | All RMSE |
| :-: | :-: | :-: | :-: | :-: | :-: | 
|irlabISI| 0.1695 | 0.2825 | - | - | - |
|SC| - | - | 0.9039 | - | - |
|irlabISI| - | - | - | 0.1132 | - |
|BJUTDMS| - | - | - | - | 0.0563 |
| :-: | :-: | :-: | :-: | :-: | :-: | 
| TFIDF+LR | - | 0.2426=>0.2642 | 0.8191=>0.8350 | - | 0.0471=>0.0454 |
| glove+RNN | - | 0.4735=>**0.5052** | 0.9038=>0.9010 | - | 0.0476=>0.0510 |
| Bert+NN | - | 0.4723 | **0.9076** | - | 0.0523 |
| - | - | - | - | - | - |

#### RNN:
><img src="image/multi-class-rnn.png" width="300"><img src="image/multi-label-rnn.png" width="315">

#### Bert fine-tuning:
><img src="image/multi-class-bert.png" width="300"><img src="image/multi-label-bert.png" width="315">

<img src="image/sheffield.png" width="500">
