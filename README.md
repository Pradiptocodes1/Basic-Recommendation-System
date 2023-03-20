# Basic-Recommendation-System
--------------------------------------------
Here, we will be implementing the memory based approach in creating the recommendation system, which solely relies on the user, ratings, and movies data and implements various types of calculations in it to find the apt movie recommendation from the user. No machine Learning algorithm was used here.
Here, there are two types of recommender systems implemented-
1. Content Based
2. Collaborative Filtering

Content Based-

Here we take the movie and rating dataset from the object storage network. First we take the movie dataset into consideration. We first extract the years by using Regex. Then we apply one hot encoding on it once on it, create a separate table for it and then load the recommendation table. then finding the rated values on the encoded table and multiplying it by the ratings (which we obtained by multiplying encoded values of the user movies with that of the movie dataset). We then normalise it. And then sort the original movie set with that values.

Colaborative filtering-

Here we take the saame approach till the extraction of data. Now in this case, the rating dataset is slightly different from that used in the content based filtering. After extracting, we also load the ratings dataset, and then apply the user input to it. Then we merge the user data with that of the movies dataset, wherein we get the original movie id and then create subsets containg other user IDs who have rated that particular input movie group. We than find the similarity using the Pearsons' Correlation method (by taking a particular set of 500 subgroups to make calculations easier), and then creating a pearsons' dataframe, taking the values from the correlation dictionary we created. In the dataframe, we first sort the values by decreasing order of similarity index, merge it with the ratings dataframe and then find the weighted rating by multiplying both. We then find the overall sum of similarity index and weighted rating for each subgroup and create another dataframe. Finally we create the ratings dataframe, taking into consideration the weighted average score, sorting the values and the find the recommendation list using that dataframe. 

Dataset used - Movie dataset (34k values) and Ratings dataset (2M values) from the IBM skill network.
