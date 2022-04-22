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

#### Data Prepartion & Exploratory Data Analysis
- Recasted the categorical variables that appeared as numeric values
- Plotly's radar plot to identify the attributes of the top 50 most popular songs
- Word cloud to identify the most common genres
- Standard visualisation techniques (boxplot, histogram, violin plot, heatmap etc.)
- Outliers were removed using the IQR method as the popularity response variable resembled a gaussian distribution


#### ML Technique 1: Regression  

#### ML Technique 2: Decision Tree Classification  
- One Hot Encoding performed on categorical variables as the variables were unordered
- Popularity score of >=80 determined as popular and <80 as not popular
- Train test split ratio of 0.2, random state = 88 to ensure better comparability of results
- Decision tree of depth 4, all song attributes, produced accuracy of 46%
- Decision tree of depth 4, top three song attributes, produced accuracy of 55%
- Decision tree of depth 6, top three song attributes, produced accuracy of 56%
- Top three song attributes that influenced popularity: artist popularity, energy, loudness

#### ML Technique 3: Random Forest Classification  
-https://towardsdatascience.com/3-techniques-to-avoid-overfitting-of-decision-trees-1e7d3d985a09#:~:text=Is%20your%20Decision%20Tree%20Overfitting,fails%20to%20capture%20important%20patterns.

#### ML Technique 4: Kmeans Clustering  

### Conclusion and Recommendations  

### Contributors  
- Graciella Theodora (@gtheo07)  
- Lee Jia Wen (@jiawen3131)
- Lim Wan Loong (@whiskeymadawg)  

### References  
- https://developer.spotify.com/
- https://newsroom.spotify.com/company-info/#:~:text=Today%2C%20Spotify%20is%20the%20world's,180m%20subscribers%2C%20across%20183%20markets.

JiaWen is trolling

