# Data Science Lovers - CSM148 Final Project

## Project Overview

For this project, our team used the “Spotify Tracks Dataset” by Maharshi Pandya on Kaggle. The dataset, in CSV format, contains 114,000 rows and 21 columns, where each row represents a unique song entry. The columns provide classification into 125 different music genres and describe various audio features and song qualities such as danceability, energy, loudness, tempo, acousticness, and instrumentalness. Our goal was to accurately classify the genres of these Spotify tracks using machine learning techniques. To simplify the problem, we consolidated the 125 genres into five primary categories: classical, electronic, rock, pop, and hip-hop/rap. Due to the limited number of hip-hop/rap tracks, we excluded this genre to balance the dataset, resulting in a four-way genre classification task.

Our methodology consisted of several key steps. First we began with data preprocessing, which included removing the few missing values, standardizing numerical features, dropping unnecessary columns, and consolidating target genres. Then, after exploratory data analysis visualizations confirmed that the dataset was roughly balanced across the four genres, we split the data into stratified 80% training and 20% testing sets. To perform classification, we selected a Random Forest model and optimized its hyperparameters such as the number of estimators and maximum depth by implementing a grid search on the training data. Using the best-performing parameters, we conducted 5-fold cross-validation to obtain a reliable average accuracy score and evaluated the final model on the unseen test data.

Our Random Forest model achieved an accuracy of 0.77 on both the training and testing sets. We believe this result is generalizable because of our use of cross-validation and the ensemble nature of Random Forest, which reduces the risk of overfitting. Additionally, achieving 77% accuracy is a significant and meaningful result considering the baseline accuracy for a four-class problem starts at only 25%. Despite these strengths, a major drawback of our design is the interpretability of the accuracy. In our case, the metrics like specificity and AUC cannot be applied which makes it harder to pinpoint exactly where errors are coming from since the task isn't binary. Another concern to note is that the random forest model, especially with grid search, can also be costly to train due to its depth. This was not much of an issue for us, but could make it difficult to generalize the model if we wanted to apply it to a much larger dataset.

Lastly, the code for our project is very straightforward to use. The only thing that needs to be done before running the notebook is to ensure that the dataset’s host library called hugging face is installed by running pip install huggingface_hub. Then our read_csv line should work properly to import the dataset, and the rest of the notebook should run without modification. Alternatively, you could download the dataset [here](https://huggingface.co/datasets/maharshipandya/spotify-tracks-dataset)

## Other Files

* The appendix for this project is located in `appendix.md`
* The code for this project is located in `final_code.ipynb`. To prevent potential Python environment issues with using this code, we recommend running this notebook in Google Colab.