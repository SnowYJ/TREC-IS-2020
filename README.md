
## Classification of tweets for aiding crisis and disaster management.

TREC-IS dataset includes two labels. One is 'categories' label involving 25 information type, which is a multi-label tweets classification. Another is 'priority' label that includes four categories. It is a multi-class tweets classification.

* system_0: dataset processing
* system_1: sklearn multi-class & multi-label Logistic Regression
* system_2: pytorch multi-class using bi-GRU and glove word embedding
* system_3: pytorch multi-label using bi-GRU and glove word embedding

dataset: http://dcs.gla.ac.uk/~richardm/TREC_IS/2020/data.html

Data augmentation: https://github.com/jasonwei20/eda_nlp

<img src="image/sheffield.png" width="500">
