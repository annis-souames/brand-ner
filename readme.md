## Named Entity Recognition for Brands in Product Titles

This projects offers a set of notebooks, models and datasets to detect brands in product titles, for instance : detecting **Zara** in "New Jeans Extra Slim Zara".

We use a cleaned and augmented version of product titles fetched from Amazon through this [dataset](https://nijianmo.github.io/amazon/index.html) which has data for over 2 million products. 

The models tested are built using spaCy and Flair and then compared. The final model files are currently not included but will be uploaded soon.

### Demo : 

<p align="center">

<img src="ressources/spacy_results.png?raw=true" width="500" height="500" />
 
</p>
<p align = "center">Results with spaCy model</p>

<p align = "center">
<img src="ressources/flair%20results.png?raw=true" />

</p>
<p align="center">Results with flair model</p>


### Paper : 

We recently wrote a paper on this project that you can download here through Research Gate : [Link to paper](https://www.researchgate.net/publication/357871883_An_end_to_end_approach_for_brand_recognition_in_product_titles_with_BI-LSTM-CRF) 

**Paper Title** : An end to end approach for brand recognition in product title using BI-LSTM-CRF.

### Installing Libraries

First you will need to install spaCy 3.x and Flair NLP Framework

`pip install spacy flair` 

As well as the common data science libraries such as Pandas, Numpy, etc. and Jupyter to run the notebooks.

## Data : 

For this project we used this large [dataset](https://nijianmo.github.io/amazon/index.html) which contains over 2M+ products, we however only included data in some categories only (computers, office supplies, etc). We then cleaned the data and applied some data augmentation as explained in the paper to balance the data (we had over 80% of titles having brands as their first word).

You can reproduce the dataset by following these steps, or you can use the cleaned and transformed final version of the data in the `datasets` folder, if you do so, you can ignore this section.


**How to rebuild the dataset using different amazon categories ?**

- Clone the project 
- Go to the notebooks folder
- Open `Clean Aamazon Data.ipynb` notebook with jupyter and replace paths with your own paths (the notebook contains a cell to download amazon data for a given category), you should re-run this notebook for each category
- Concatenate results data files(amazon_computers.csv, amazon_food.csv, amazon_office.csv), these files are included in the data folder along with their concatenation so you can ignore this step if you want to use the exact same datase
- Convert your CSV files to spaCy binary files, json files and BIO scheme using the `Dataset converter.ipynb` notebook.



## Pretrained models


### Flair :

The flair model is too heavy to include in this repo (over 300 mb), you can download the `model.pt` file here in Google Drive : [Download the model](https://drive.google.com/file/d/10uTAFSVuv0u_BVMYz8kV7gJtQN9dsw9j/view?usp=sharing).

Once downloaded you should put it somewhere in this repo, and run the last cell of the `Flair NER Model.ipynb` to test it. You can of course deploy it too using Flask or other backend frameworks.

### spaCy : 

In the models folder you will find a pretrained spacy model that gave an f1-score of 0.84 along with generated spaCy static vectors ready to use (we used Word2Vec to generate embeddings than the `spacy init` command to generate the static vectors), the model is in `models\spacy\ner_amazon_embeddings` while the static vectors are in `spacy_embeddings`.



## Training Models

In this project we trained two models : two using custom Word2Vec embeddings and spaCy and the second one using Flair with GloVe embeddings and Flair embeddings

**spaCy Model**

In order to train the spaCy model you need to have `train.spacy` and `test.spacy` in the datasets/amazon/spacy folder, the original train and test files have been included but you can generate your own using the `Dataset converter.ipynb` notebook as explained above. 

Once you have your data files ready in spacy format, head to cmd.txt and config.cfg, at this moment you should check the spaCy documentation to edit the config.cfg file to train your model. 

The `cmd.txt` file contains set of spaCy commands to run the model.

**Note :**  If you decide to use the custom word embeddings, you should first run the `embeddings.ipynb` notebook and then look up in the spaCy documentation how to generate spacy static vectors which can be saved to a folder than run it using the commands in the cmd.txt file.


**Flair Model**

In order to retrain the Flair model, which gave slightly better results, you should make sure that you have pytorch and flair installed along with a good GPU, RAM and internet connection, we advise to use Google Colab is you don't have a GPU. 

After that just run `Flair NER Model.ipynb` using the right paths for the data. You can find [Flair documentation here](https://github.com/flairNLP/flair).


## Cite and contribute :

In case you use this project in a research project, please cite our paper : 

Mohamed Annis Souames, Larbi Abderrahmane Mohammedi "An end to end approach to brand recognition in product titles using BI-LSTM-CRF", 2022


If you found errors or bugs, please create an issue, and if you enjoyed this project please give us a star !


## Contributors

- Mohamed Annis Souames - Ecole Nationale Polytechnique, Algiers

- Larbi Abderrahmane Mohammedi - Ecole Nationale Polytechnique, Algiers 