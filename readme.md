## Named Entity Recognition for Brands in Product Titles

This projects offers a set of notebooks, models and datasets to detect brands in product titles, for instance : detecting **Zara** in "New Jeans Extra Slim Zara".

We use a cleaned and augmented version of product titles fetched from Amazon through this [dataset](https://nijianmo.github.io/amazon/index.html) which has data for over 2 million products. 

The models tested are built using spaCy and Flair and then compared. The final model files are currently not included but will be uploaded soon.

### Demo : 

![spaCy Resuls](ressources/spacy_results.png?raw=true "Results of model built with spaCy")
![Flair Resuls](ressources/flair%20results.png?raw=true "Results of model built with Flair")

### Paper : 

We recently wrote a paper on this project that you can download here through Research Gate : [Link to paper](https://www.researchgate.net/publication/357871883_An_end_to_end_approach_for_brand_recognition_in_product_titles_with_BI-LSTM-CRF) 

**Paper Title** : An end to end approach for brand recognition in product title using BI-LSTM-CRF.

### Installing Libraries

First you will need to install spaCy 3.x and Flair NLP Framework

`pip install spacy flair` 

As well as the common data science libraries such as Pandas, Numpy, etc. and Jupyter to run the notebooks.

### Data : 

For this project we used this large [dataset](https://nijianmo.github.io/amazon/index.html) which contains over 2M+ products, we however only included data in some categories only (computers, office supplies, etc). We then cleaned the data and applied some data augmentation as explained in the paper to balance the data (we had over 80% of titles having brands as their first word).

You can reproduce the dataset by following these steps, or you can use the cleaned and transformed final version of the data in the `datasets` folder, if you do so, you can ignore this section.


**How to rebuild the dataset using different amazon categories:**

- Clone the project 
- Go to the notebooks folder
- Open Clean Aamazon Data and replace paths with your own paths (the notebook contains a cell to download amazon data for a given category), you should re run this notebook for each category
- Concatenate results data files(amazon_computers.csv, amazon_food.csv, amazon_office.csv), these files are included in the data folder along with their concatenation so you can ignore this step if you want to use the exact same dataset

