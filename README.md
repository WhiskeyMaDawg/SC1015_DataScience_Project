# SC1015 DataScience Project - _Spotify Music Analysis_

<img width="850" alt="image" src="https://user-images.githubusercontent.com/90097030/164615136-60684cdc-bec6-428e-bd1c-d0afde7ac777.png">

### Description  
Music streaming has been an integral part of our lives. There is a whopping 406 millions users worldwide who are using spotify for music streaming. With this amount of user counts, streaming music platforms are using data collected by consumer interaction in an effort to hone their algorithms, improve user experiences, target audiences with ads, and make overall better-informed business decisions. 

### Problem Definition  
Using the data available,  
- How important are the attributes in predicting popularity?  
- Whether there are any attributes that can be tweaked to increase popularity?  

### Dataset
Spotify stores a lot of songs data in its database. We make use of its Spotify API and the python Spotipy package to access and extract the songs data that we need in the playlist. Examples such as the song's titles, artists and numerous attributes of the songs.

### [1. Data Prepartion & Exploratory Data Analysis](https://github.com/WhiskeyMaDawg/SC1015_DataScience_Project/blob/main/Data_Preparation_%26_Exploratory_Data_Analysis.ipynb)
- Recasted the categorical variables that appeared as numeric values
- Plotly's radar plot to identify the attributes of the top 50 most popular songs
- Word cloud to identify the most common genres
- Standard visualisation techniques (boxplot, histogram, violin plot, heatmap etc.)
- Outliers were removed using the IQR method as the popularity response variable resembled a gaussian distribution


### 2. ML Technique 1: Regression  

### 3. ML Technique 2: Decision Tree Classification  
- One Hot Encoding performed on categorical variables as the variables were unordered
- Popularity score of >=80 determined as popular and <80 as not popular
- Train test split ratio of 0.2, random state = 88 to ensure better comparability of results
- Decision tree of depth 4, all song attributes, produced accuracy of 46%
- Decision tree of depth 4, top three song attributes, produced accuracy of 55%
- Decision tree of depth 6, top three song attributes, produced accuracy of 56%

The top three song attributes that influenced popularity: **artist popularity, energy, loudness**

### 4. ML Technique 3: Random Forest Classification  
-https://towardsdatascience.com/3-techniques-to-avoid-overfitting-of-decision-trees-1e7d3d985a09#:~:text=Is%20your%20Decision%20Tree%20Overfitting,fails%20to%20capture%20important%20patterns.

### 5. ML Technique 4: Kmeans Clustering
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

JiaWen is trolling

