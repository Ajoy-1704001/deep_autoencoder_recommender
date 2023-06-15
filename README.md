# deep_autoencoder_recommender
## How to run the code
### prerequisite
 - Must need GPU support
 - Pytorch
### Preprocessing
1. At first import the program.ipynb file into notebook editor (Preffered Platform: Kaggle)
2. Then load the dataset.
    - Movielens Dataset:
    '''python
    !wget https://files.grouplens.org/datasets/movielens/ml-20m.zip
    !unzip ml-20m.zip
    '''
    - Yelp Dataset: <a ref="">Click here</a> (You have to select this file yelp_academic_dataset_review.json)
    - Netflix Prize Dataset: <a ref="https://www.kaggle.com/datasets/netflix-inc/netflix-prize-data">Click here</a>
3. Now import all the necessary library
4. Then filter out minimum number of interaction and split userId at ratio of 8:1:1(Train: Test: Validation)
5. According to the ratio, map each userId with interacted itemId and create Train, Test and validation set.
6. Sometimes CPU may crash due to heavy computation. So we may save these sets into separated csv
### Model Training
1. Now for model training we must enable gpu support.
2. We have to import those saved csv (Preprocessing step:6)
3. Now we have to define our model class, functions and related parameters. We also have to define our evalution metrices such as nDCG@100, Recall@50 and Recall@20.
4. Then we can run model. It will show us best validation nDCG score.
5. We can adjust the latent dimension, hidden dimension, batch size etc. according to our need.
6. After training we can test our model with test data.

## Special Note:
For Yelp Dataset:
- I have taken userId and stars feature.
- UserId aren't decimal or float value. We have to index it properly.

## Some parameters:
Heldout users number:
  ML Dataset: 10000 users
  Yelp Dataset: 80000 users
  Netflix Prize Dataset: 40000 users
 Try to keep Beta around 1.4 to 2
 
 
 For any Query:
 Knock me at ajoydeb.cuet@gmail.com
