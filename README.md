# MovieLens-Recommendation-System-using-R

# Introduction

The MovieLens dataset, a widely-used benchmark in the field of recommender systems, provides a wealth of information about user ratings and movie metadata. 

This dataset offers an excellent opportunity to explore user behavior, movie popularity, and the dynamics of the movie industry.

In this project, we will conduct a comprehensive analysis of the MovieLens dataset, focusing on the following aspects:

Kaggle Website Link for the Dataset: https://www.kaggle.com/code/colinmorris/movielens-preprocessing/input

**Data Exploration**: Understanding the structure, size, and key features of the dataset.

**Data Cleaning and Preprocessing:** Identifying and handling missing values, outliers, and inconsistencies in the data.

**Exploratory Data Analysis (EDA)**: Visualizing and analyzing the distribution of ratings, user activity, and movie popularity.

**Recommendation Systems:** Building and evaluating different recommendation models, such as collaborative filtering, content-based filtering, and hybrid approaches.

# Structure of the Movie Dataset:

•	**Dimensions:** The dataset consists of 10,329 rows and 3 columns.

**•	Data Types:** 
o	**movieId**: Numeric (likely integer)

o	**title**: Character (string)

o	**genres**: Character (string)

**Column** **Descriptions:**
•	**movieId**: A unique identifier for each movie.

•	**title**: The title of the movie.

•	**genres**: A string representing the movie's genres, separated by the '|' character.

# Structure of the Ratings Dataset:

•	**Dimensions**: The dataset consists of 105,339 rows and 4 columns.

**•	Data Types: **

o	**userId**: Numeric (likely integer)

o	**movieId**: Numeric (likely integer)

o	**rating**: Numeric (likely float or integer)

o	**timestamp**: Numeric (likely timestamp or Unix time)

**Column Descriptions:**
•	**userId**: A unique identifier for each user.

•	**movieId**: A unique identifier for each movie.

•	**rating**: The rating given by a user to a movie (likely on a scale of 1 to 5).

•	**timestamp**: The timestamp of the rating.

# Bar Chart for Genre Distrbiution

![image](https://github.com/user-attachments/assets/fcb5ada5-9e3e-4586-a976-e2dc878bafb5)

**Observations**:

**•	Drama Dominance:** The "Drama" genre clearly stands out as the most prevalent genre, with a significantly higher count compared to other genres.

**•	Diverse Genre Representation:** The dataset covers a wide range of genres, from popular choices like Action, Comedy, and Adventure to niche genres like Film-Noir and IMAX.

**•	Genre Overlap**: It's likely that many movies belong to multiple genres, as indicated by the relatively high counts for some genres.

# Validation Set: A Crucial Component in Machine Learning

A validation set is a portion of a dataset used to assess the performance of a machine learning model during the training process. 

It helps in tuning hyperparameters and preventing overfitting. 

![image](https://github.com/user-attachments/assets/c3825f13-1e1c-4406-a23c-8ca67518cb4c)

A (a data frame-like structure) was created to summarize the number of ratings in different datasets: 

This tibble provides a clear and concise summary of the number of ratings in each dataset, making it easy to compare and analyze.  

The rows were filtered from one data frame based on the presence of matching values in another data frame. 

In simpler terms, it keeps only those rows from the first data frame that have a match in the second data frame. 

By adding the removed rows back to the working set, we ensure that all data points are used for training. 

This can potentially improve the model's performance, especially if the removed rows contain valuable information.

# Data Visualization for Rating Distribution

![image](https://github.com/user-attachments/assets/b7c05cc8-7328-421a-917f-e764decd97c4)

**Observations:**

**•	Most Common Ratings:** The most frequent ratings are 4.0 and 4.5.

**•	Fewer Lower Ratings:** There are fewer ratings for 0.5, 1.0, and 1.5, suggesting that users tend to give higher ratings.

**•	Decreasing Trend:** The number of ratings decreases as the rating value increases from 4.5 to 5.0.


**Potential Insights:**

**•	User Tendency:** Users seem to be more inclined to give positive ratings.

**•	Movie Quality:** The majority of movies in the dataset might be of relatively high quality.

# Timestamp Based Data Analysis

The analysis shows a sample of 20 timestamps extracted from the working_set data frame. 

These timestamps are in UTC format, indicating Coordinated Universal Time.

# The Number of Ratings in each Year or The Ratings Per Year

![image](https://github.com/user-attachments/assets/e1d39b9b-a8c9-4799-80dc-2291715e6c79)

**Observations:**

**•	Peak Years:** There are a few years with significantly higher numbers of ratings, indicating peak periods of activity.

**•	Fluctuations**: The number of ratings fluctuates from year to year, suggesting varying levels of user activity and movie releases.

**•	Overall Trend**: There seems to be a slight increasing trend in the number of ratings over time.

# Average Rating Per Year

![image](https://github.com/user-attachments/assets/70d99090-3ab8-4810-9e45-7fcaf2af8c54)

**Observations:**

•	**Overall Trend:** The average rating per year seems to fluctuate around a relatively stable value. There's no significant upward or downward trend.

**•	Year-to-Year Variation:** There are variations in the average rating from year to year, but these fluctuations appear to be relatively small.

# Analyzing the Movie Popularity Summary

![image](https://github.com/user-attachments/assets/27fc7bb1-82fd-4df2-910b-f0857c4e8835)

**Key Observations:**

**•	Min**: The least popular movie has only 1 rating.

**•	1st Quartile**: 25% of the movies have 1 or fewer ratings.

**•	Median:** The median number of ratings is 2, meaning that half of the movies have 2 or fewer ratings.

**•	Mean:** The average number of ratings per movie is 9.218.

**•	3rd Quartile:** 75% of the movies have 7 or fewer ratings.

**•	Max:** The most popular movie has 296 ratings.

**Potential Insights and Further Analysis:**

1.	**Long Tail Distribution:** The data likely follows a long-tail distribution, where a few movies have a large number of ratings, while most movies have relatively few ratings.
   
2.	**Popular Movies**: The movies with a high number of ratings are likely to be popular and influential.

# Data Visualization for Rating Per Movie

![image](https://github.com/user-attachments/assets/f09eae20-bba9-4e18-abb3-fce6c4b72bdf)

**Observations**:

**•	Long-Tail Distribution:** The plot clearly shows a long-tail distribution, where a few movies have a very large number of ratings, while most movies have relatively few ratings.

•	**Outliers**: There are a few movies with extremely high numbers of ratings, which are considered outliers.

**•	Overall Trend**: The number of ratings decreases as the movie rank increases

# Histogram for Movie Rating

![image](https://github.com/user-attachments/assets/b8d112b4-b4d7-4499-8084-c2d28ab453a6)

**Key Observations**:

**•	Long-Tail Distribution**: The histogram shows a long-tail distribution, meaning that most movies have a relatively small number of ratings, while a few movies have a large number of ratings.

**•	Majority of Movies Have Few Ratings:** A significant portion of the movies have less than 10 ratings.

**•	Fewer Movies with Many Ratings**: As the number of ratings increases, the number of movies decreases.

# Rating Per User Visualization

![image](https://github.com/user-attachments/assets/c782b2ce-69a0-4b40-870f-4739d1cd2641)

**Observations:**

•**Long-Tail Distribution**: The plot shows a long-tail distribution, indicating that a few users have given a large number of ratings,

while most users have given a relatively small number of ratings.

•**Outliers**:There are a few outliers, representing users who have given an exceptionally large number of ratings.

# Histogram for User Rating

![image](https://github.com/user-attachments/assets/0f1406e4-2db6-4bee-8227-e8f8e4404b7a)

**Key Observations:**

**•	Long-Tail Distribution**: The histogram shows a long-tail distribution, meaning that most users have given a relatively

small number of ratings, while a few users have given a large number of ratings.

**•	Majority of Users Give Few Rating**s: A significant portion of users have given less than 100 ratings

**•	Fewer Users Give Many Ratings**: As the number of ratings increases, the number of users decreases.

# Matrix Visualization for User Movie

![image](https://github.com/user-attachments/assets/a7806657-0267-46b7-89ae-ca2a61efb399)


•	Rows represent users.

•	Columns represent movies.

•	A cell with a value (e.g., a dot) indicates that a user has rated a specific movie.

**Potential Insights and Analysis:**

**Sparse Matrix:**
	
o	The matrix is likely sparse, meaning most cells are empty. This implies that most users have not rated most movies.

This sparsity is a common characteristic of recommendation systems datasets.

**User and Movie Activity:**

o**Active Users:** Identify users with many ratings (rows with many dots). These users can be valuable for understanding overall trends and preferences.

o	**Popular Movies:** Identify movies with many ratings (columns with many dots). These movies are likely to be popular and can be used as a starting point for recommendations.

**User-Movie Interactions:**

o	Analyze the patterns of user-movie interactions to understand how users discover and rate movies.

o	Identify co-watched movies or similar ratings patterns among users.

# Frequency for Genre
From the data analysis for Genre, it appears that action, adventure, animation, and children's movies are popular genre combinations.

**Potential Insights and Analysis:**
1.	**Popular Genres:**
   
o	**Action, Adventure, Comedy, and Drama**: These genres have the highest number of movies, indicating their popularity among viewers.

o	**Niche Genres**: Genres like Film-Noir and Western have fewer movies, suggesting a niche audience.

# Visualization for Genre Popularity

![image](https://github.com/user-attachments/assets/23b07508-6aee-411b-af55-b9d2ecbc0029

**Key Observations:**

**•	Popular Genres:** 
o	**Drama**:Drama is the most popular genre, with the highest number of ratings.

o	Comedy, Action, and Adventure: These genres also have a significant number of ratings.

**•	Less Popular Genres:**
o	Genres like Film-Noir, Musical, and Documentary have relatively fewer ratings.

# Visualization for Genre Average Rating

![image](https://github.com/user-attachments/assets/fc764b6d-2c1b-4813-b817-0247db2b739e)

**Key Observations:**

**•	Genre-Specific Ratings**: Different genres have varying average ratings.

**•	Higher-Rated Genres:** Genres like Film-Noir, Fantasy, and Documentary tend to have higher average ratings.

**•	Lower-Rated Genres**: Genres like Children's and Musical tend to have lower average ratings.

# Research Questions and Answers Based on the MovieLens Dataset Analysis

•	**Research Question 1:** What is the distribution of ratings in the dataset?

•**	Answer:** The dataset exhibits a long-tail distribution, with a significant number of movies receiving few ratings and a smaller number of movies receiving many ratings. 
The most frequent rating is 4.


**•	Research Question 2**: What are the most popular genres in the dataset?

•	**Answer**: Drama is the most popular genre, followed by Comedy, Action, and Adventure. Genres like Film-Noir, Musical, and Documentary are less popular.


•**	Research Question 3:** How does user activity vary?

•	**Answer**: The distribution of user activity is skewed, with a few highly active users and many users who have rated only a few movies. 
This suggests that a small portion of users contributes significantly to the overall rating activity.


# Data Split

o	The dataset has been split into a training set and a test set. 

This is a common practice in machine learning to train a model on a portion of the data and evaluate its performance on a held-out portion.

o	The temp_test_set might be a temporary set used for specific purposes, such as hyperparameter tuning or model selection.

**Dataset Size:**

o	The original dataset contains 105,339 ratings.

o	The training set contains 94,805 ratings, which is a significant portion of the original dataset.

o	The test set contains 10,534 ratings, which is a smaller subset.

# Evaluation Results
<img width="191" alt="image" src="https://github.com/user-attachments/assets/05089710-7cad-49fa-8e9d-6e9e666a0cf6">

The table provides a comparison of three recommendation models: Cinematch, The Netflix Prize, and Random Guessing,

based on their Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

Key Observations:
****
**Missing Values for Cinematch and Netflix Prize**: The MAE and MSE values for Cinematch and The Netflix Prize are missing. 

This could be due to various reasons, such as missing data or errors in the calculation.

**Random Guessing Baseline:** The Random Guessing model serves as a baseline to compare the performance of the other models. 

It has the highest MAE and RMSE values, indicating poor performance.

**Interpreting the Results:**

**Lower MAE and RMSE**: Lower values for MAE and RMSE indicate better model performance.

**MAE**: Measures the average absolute difference between the predicted and actual ratings.

**RMSE**: Measures the square root of the average squared difference between the predicted and actual ratings.

# Recommendations and Conclusion

# Recommendations

Based on the analysis of the MovieLens dataset, here are some recommendations for further exploration and potential applications:

**1.	Recommendation Systems:**

**o	Collaborative Filtering**: Utilize user-based and item-based collaborative filtering techniques to recommend movies based on similar users or similar movies.

**o	Content-Based Filtering:** Recommend movies based on their genre, director, or plot similarity.

o	**Hybrid Approaches**: Combine collaborative and content-based filtering for more accurate recommendations.

o	**Matrix Factorization**: Employ matrix factorization techniques to uncover latent factors that explain user preferences and movie characteristics.

**2.	User Behavior Analysis:**

o	Study user rating patterns, such as the frequency of ratings and the distribution of ratings.

o	Identify active and inactive users to tailor recommendations accordingly.

**3.	Movie Popularity Analysis:**
	
o	Analyze the popularity of movies over time and identify trends.

o	Explore the relationship between movie popularity and genre, director, or release year.

**4.	Genre Analysis:**
	
o	Analyze the popularity of different genres and genre combinations.

o	Identify emerging trends in genre preferences.

**5.	Data Visualization:**
	
o	Use visualizations to explore the data and identify patterns.

o	Create visualizations to communicate insights to stakeholders.

# Conclusion

The MovieLens dataset provides a rich source of information for understanding user preferences, 

movie popularity, and the dynamics of the movie industry. By analyzing the data and applying various techniques, 

we can gain valuable insights and build effective recommendation systems.
