## Anime User Behavior Analysis

### Table of Contents
1. [Introduction](#introduction)
2. [Data Collection and Wrangling](#data-collection-and-wrangling)
3. [Exploratory Data Analysis (EDA)](#eda)
4. [Data Pre-processing](#data-preprocessing)
5. [Model Building, Training, and Evaluation](#model-building)
6. [Conclusion and Recommendations](#conclusion)
7. [Future Work](#future-work)

### <a name="introduction"></a>1. Introduction and Problem Identification
Our objective is to enhance the anime viewing experience by understanding user behaviors around anime consumption. By studying user preferences and ratings, our goal is to create a recommender system to help streaming platforms curate a better viewing experience.

### <a name="data-collection-and-wrangling"></a>2. Data Collection and Wrangling
**Datasets Used:**
- [Detailed User Data](https://www.kaggle.com/datasets/azathoth42/myanimelist?select=UserList.csv)
- [Comprehensive Anime List with Metadata](https://www.kaggle.com/datasets/azathoth42/myanimelist?select=AnimeList.csv)
- [User Interactions and Ratings Data](https://www.kaggle.com/datasets/azathoth42/myanimelist?select=UserAnimeList.csv)

The data was loaded, filtered for essential columns, and merged to provide a comprehensive dataset for analysis.

### <a name="eda"></a>3. Exploratory Data Analysis (EDA)
Key insights gathered:
- Distribution of anime ratings by users
- Number of anime rated by users

### <a name="data-preprocessing"></a>4. Data Pre-processing and Addressing Challenges
- Users were filtered based on their number of rated anime to handle the cold start problem.
- The data dimensions were reduced to a more manageable size after merging the datasets.

### <a name="model-building"></a>5. Model Building, Training, and Evaluation
**Metrics Used:** Precision@k and Recall@k, known for their significance in evaluating recommender systems.

**Models Tested:** 
- SVD
- SlopeOne
- NMF
- KNN variants
- BaselineOnly

**Key Findings:**
- `BaselineOnly` was the best model in terms of RMSE and Precision@10.
- Despite using GridSearchCV for hyperparameter tuning, default parameters produced the best RMSE.
- The final recommender system was built using `BaselineOnly`, predicting potential ratings for user-anime pairs. We then designed a function to suggest the top anime for any given user based on these predictions.

### <a name="conclusion"></a>6. Conclusion and Recommendations
The `BaselineOnly` recommender system can be an asset for streaming platforms, suggesting top anime recommendations for viewers. Streaming platforms can use this system to customize their user interfaces, emphasizing top-rated anime, leading to increased user engagement.

### <a name="future-work"></a>7. Future Work
- Tackling the cold start problem for newcomers or anime.
- Incorporating content-based filtering alongside collaborative filtering to improve recommendation precision.
- Enabling real-time user feedback to dynamically adjust the recommendation list.
