# SC1015 DataScience Project - _Spotify Music Analysis_

<img width="850" alt="image" src="https://user-images.githubusercontent.com/90097030/164615136-60684cdc-bec6-428e-bd1c-d0afde7ac777.png">

### Description  
Music streaming has been an integral part of our lives. There is a whopping 406 millions users worldwide who are using spotify for music streaming. With this amount of user counts, streaming music platforms are using data collected by consumer interaction in an effort to hone their algorithms, improve user experiences, target audiences with ads, and make overall better-informed business decisions. 

### Problem Definition  
Using the data available,  
- How important are the attributes in predicting popularity?  
- Whether there are any attributes that can be tweaked to increase popularity?  

### [Dataset](dataset/SpotifyFinalAPI.csv)
Spotify stores a lot of songs data in its database. We make use of its Spotify API and the python Spotipy package to access and extract the songs data that we need in the playlist. Examples such as the song's titles, artists and numerous attributes of the songs.

### [1. Data Prepartion & Exploratory Data Analysis](https://github.com/WhiskeyMaDawg/SC1015_DataScience_Project/blob/main/Data_Preparation_%26_Exploratory_Data_Analysis.ipynb)
- Recasted the categorical variables that appeared as numeric values
- Plotly's radar plot to identify the attributes of the top 50 most popular songs
- Word cloud to identify the most common genres
- Standard visualisation techniques (boxplot, histogram, violin plot, heatmap etc.)
- Outliers were removed using the IQR method as the popularity response variable resembled a gaussian distribution


### [2. ML Technique 1: Regression](Regression_Model.ipynb)  
- R^2 measures the strength of the relationship between the model and the dependent variable on a scale of 0 to 1. The higher the R^2, the better the model.
- Mean Squared Value (MSE) tells you how close the regression line is to a set of points. The lower the MSE, the better the model.
- Univariate:  all the R^2 value were very close to 0 & MSE is close to 40 which is rather high for a popularity score ranging from 0 to 100.
- Multivariate: R^2 is close to 0 and MSE is close to 40, which is still not accurate in predicting the popularity
- Decision Tree: R^2 and MSE improves significantly for train data but still perform poorly in the test data with similar value as other regression model.
- Random Forest: Best result out of all the regression model, but still not very satisfactory even when we tuned to the optimal hyper-parameter using GridSearchCV.

### [3. ML Technique 2: Decision Tree Classification](Decision_Tree_(Outliers_IQR).ipynb)  
- One Hot Encoding performed on categorical variables as the variables were unordered
- Popularity score of >=80 determined as popular and <80 as not popular
- Train test split ratio of 0.2, random state = 88 to ensure better comparability of results
- Decision tree of depth 4, all song attributes, produced accuracy of 46%
- Decision tree of depth 4, top three song attributes, produced accuracy of 55%
- Decision tree of depth 6, top three song attributes, produced accuracy of 56%

The top three song attributes that influenced popularity: **artist popularity, energy, loudness**

### [4. ML Technique 3: Random Forest Classification](Random_Forest_Classification.ipynb) 
-	Similar to decision tree but with **more hyper-parameters**
-	**Forest 1**: 100 trees and depth = 10
-	**Forest 2**: 1000 trees and depth = 10
-	**Forest 3**: 100 trees and depth = 20
-	The accuracy for the different forests was about the same at 55%, and shows a sign of over-fitting in the train data
-	Tune to the optimal hyper-parameter using GridSearchCV, with 600 trees and depth = 7, accuracy improves but not significant (60%), over-fitting problem has reduced too
-	Overall, it is the best ML technique to be used to predict the popularity as it produces the highest accuracy out of all the models we have tried.  

The top three attributes that affect the popularity: **artist_popularity, energy, loudness**

### [5. ML Technique 4: Kmeans Clustering](KMeans_Clustering.ipynb)
- Clusters from 1 to 40 ran and elbow plot visualised to determine the optimal number of clusters that reduces within sum of squares (WSS)
- Cluster size of 5 chosen as it allowed for a steep decrease is WSS value
- Songs with higher popularity have higher artist popularity
- Songs with higher popularity have slightly higher danceability
- Songs with higher popularity also have slightly higher acousticness value
- Songs with lower popularity has lower value of acousticness

The **artist's popularity and danceability** can increase a song's popularity.

### Conclusion
- Songs' popularity can be predicted with a prediction accuracy of **~60%**
- To increase a song's popularity, the features of **danceability, energy and loudness** can be tweaked
- **Artist's popularity** is still a key factor in a song's popularity

### Limitations and Recommendations 
- A song's popularity is not solely determined by these numeric attributes. Hence, other attributes like the key, mode and duration of a song can be analysed.
- A song's popularity is also not determined only by its numeric attributes. For instance, the lyrics of a song could be what makes it popular. A deeper dive into common lyrics/ words used in popular songs can be explored.
- Our categorical data like speechiness and liveness showed a huge class imbalance. Hence, we should increase the data set to include songs from various playlists, that can allow for a more even spread

### Contributors  
- Graciella Theodora (@gtheo07)  
- Lee Jia Wen (@jiawen3131)
- Lim Wan Loong (@whiskeymadawg)  

### References  
- https://developer.spotify.com/
- https://newsroom.spotify.com/company-info/#:~:text=Today%2C%20Spotify%20is%20the%20world's,180m%20subscribers%2C%20across%20183%20markets.
- https://www.statisticshowto.com/probability-and-statistics/statistics-definitions/mean-squared-error/#:~:text=The%20mean%20squared%20error%20(MSE,to%20remove%20any%20negative%20signs.
- https://towardsdatascience.com/3-techniques-to-avoid-overfitting-of-decision-trees-1e7d3d985a09#:~:text=Is%20your%20Decision%20Tree%20Overfitting,fails%20to%20capture%20important%20patterns.
