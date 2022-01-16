## Named Entity Recognition for Brands in Product Titles

This projects offers a set of notebooks, models and datasets to detect brands in product titles, for instance : detecting **Zara** in "New Jeans Extra Slim Zara".

We use a cleaned and augmented version of product titles fetched from Amazon through this [dataset](https://nijianmo.github.io/amazon/index.html) which has data for over 2 million products. 

The models tested are built using spaCy and Flair and then compared. The final model files are currently not included but will be uploaded soon.

### Paper : 

We recently wrote a paper on this project that you can download here through Research Gate : [Link to paper](https://www.researchgate.net/publication/357871883_An_end_to_end_approach_for_brand_recognition_in_product_titles_with_BI-LSTM-CRF) 

**Paper Title** : An end to end approach for brand recognition in product title using BI-LSTM-CRF.

### Installing Libraries

First you will need to install spaCy 3.x and Flair NLP Framework

`pip install spacy flair` 

Besides the common data science libraries such as Pandas, Numpy, etc. and Jupyter to run the notebooks.

### Data : 

For this project we used this large [dataset](https://nijianmo.github.io/amazon/index.html) which contains over 2M+ products, we however only included data in some categories only (computers, office supplies, etc).

