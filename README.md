# UserBasedCollaborativeFiltering
Project I worked on during my Data Science Course at WBS Coding School in Berlin, 11/2021.

**Building a User-Based Recommender based on Cosine Similarity** 

[Used Library](https://scikit-learn.org/stable/)


Work in Progress 😊 keep iterating! 

# Overview

Implement a simple user-based collaborative filtering recommender system to predict the ratings of an movie using the data given. 
The code then is to predict the ratings based on User similarity and uses the Cosine Similarity for computing similarities between users. To test the results data was divided into training and test sets. To improve results , K-Nearest_Neighboor as a neighborhood-based filtering method was used. It is to find an alternative solution to the **.fillna()**-method to replace NaN to decrease impact of NULLs to the prediction results. 

# Requirements
========================

*read data and (merge tables that carry necessary data) & pivot so that row = 'userId' and columns = 'MovieId'|'title'*

1. Replace NaNs (tbi)
2. Compute pairwise cosine similarities and create Similarity Matrix [check here](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise.cosine_similarity.html)
3. Building Recommender Function (exclude imputed user(!))
   - Compute weights and accumulate them
   - Compute weighted averages AS rating predictions
   - Try neighborhood-based filtering using KNN
4. Train-Test-Split
   - extracting the rating-positions as new dataframe (2 columns = 1. column = index.pos, 2. column = column.pos) and split into train and test (=train_pos/test_pos)
   - Create empty dataframe (0) in the shape of the pivot table that contains ratings (columns = movies, rows = users)
   - Fill the values to the right positions in the corresponding dataframe (train and test (train_test_pos))
   - Train model by computing the similarites for the train set
   - Predict all rating positions
   - Check results on train and test set 
5. Visualize Results
6. Other ways of evaluation [check](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_squared_error.html)


# Data

This dataset (ml-latest-small) describes 5-star rating and free-text tagging activity from [MovieLens](http://movielens.org), a movie recommendation service. It contains 100836 ratings and 3683 tag applications across 9742 movies. These data were created by 610 users between March 29, 1996 and September 24, 2018. This dataset was generated on September 26, 2018.

Users were selected at random for inclusion. All selected users had rated at least 20 movies. No demographic information is included. Each user is represented by an id, and no other information is provided. Each user has rated at least 20 movies.

The data are contained in the files `links.csv`, `movies.csv`, `ratings.csv` and `tags.csv`. More details about the contents and use of all these files follows.

This is a *development* dataset. As such, it may change over time and is not an appropriate dataset for shared research results. See available *benchmark* datasets if that is your intent.

This and other GroupLens data sets are publicly available for download at <http://grouplens.org/datasets/>.
#Citation:  F. Maxwell Harper and Joseph A. Konstan. 2015. The MovieLens Datasets: History and Context. ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4: 19:1–19:19. <https://doi.org/10.1145/2827872>

The dataset files are written as [comma-separated values] (http://en.wikipedia.org/wiki/Comma-separated_values) files with a single header row. 


