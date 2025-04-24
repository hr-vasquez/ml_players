# Machine Learning Project
Author: Rodrigo Vasquez
## Overview
This project focuses on PS players characteristics to be able to split them into groups. The dataset contains information about players, the games they bought, the achievements they did and the games information. Dataset location: https://www.kaggle.com/datasets/artyomkruglov/gaming-profiles-2025-steam-playstation-xbox
## Data Understanding
The data is splitted into 6 csv files: achievements.csv, games.csv, history.csv, players.csv, prices.csv, purchased_games.csv. The steps I followed:
* Calculate the number of games purchased by each player
* Get the number of top achievements for each player
* Get the number of medium achievements for each player
* Get the number of low achievements for each player
* Calculate the most frequent genre by each player
* Calculate the total money spent by each player
* Calculate a timestamp for how fast the player make its first achievement
* Calculate the date of last achievement by player
* Calculate the date when the player started working
## Data Engineering
Steps done to clean the data:
* Removed missing values (there was not too much)
* Some outliers were kept (for players with extreme stats)
* Some outliers were replaced by the label "Others"
* All players without any achievement were removed because dataset is not complete
## Model Training and Evaluation
The data was normalized using the MinMax and Standard techniques. The following models were applied:
### K-Means
It was analyzed the best K for MinMax and Standard datasets. A chart was provided to see how the clusters are distributed.
### DBSCAN
It was analyzed the best eps and min_samples for MinMax and Standard datasets. A chart was provided to see how the clusters are distributed.
### Agglomerative Clustering
It was analyzed the best number of clusters for MinMax and Standard datasets. A chart was provided to see how the clusters are distributed.
## Model Comparisson
'|    | Model         | Normalization   |   Number of Clusters | Silhouette Score    | Davies-Bouldin Index   | Calinski-Harabasz Score   |\n|---:|:--------------|:----------------|---------------------:|:--------------------|:-----------------------|:--------------------------|\n|  0 | K-Means       | MinMax          |                    2 | 0.17537957393000053 | 2.2248380073187466     | 804.941064602819          |\n|  1 | K-Means       | Standard        |                    5 | 0.12873577093604635 | 1.811895*              | 638.1685731880492         |\n|  2 | DBSCAN        | MinMax          |                    2 | 0.1693067769959489  | 2.3616747880570736     | 11.196667886611754        |\n|  3 | DBSCAN        | Standard        |                    2 | 0.645072*           | 2.6190475899960632     | 115.13446714871299        |\n|  4 | Agglomerative | MinMax          |                    2 | 0.1823598251525272  | 2.0860089909479433     | 816.791435*               |\n|  5 | Agglomerative | Standard        |                    4 | 0.11671582629170589 | 1.958455014531524      | 561.7860443789965         |'
