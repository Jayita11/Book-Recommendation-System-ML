# Book Recommendation System

![Book Recommendation System](https://img.shields.io/badge/Recommendation%20System-Book-brightgreen)

## Table of Contents

- [Overview](#overview)
- [Objective](#objective)
- [Dataset](#dataset)
- [Features](#features)
- [Model and Data Artifacts](#model-and-data-artifacts)
- [Model Evaluation](#model-evaluation)
- [Deployment](#deployment)
- [Future Work](#future-work)



## Overview

Recommendation systems are becoming increasingly important in today's extremely busy world. People are always short on time with the myriad tasks they need to accomplish in the limited 24 hours. Therefore, recommendation systems are important as they help them make the right choices, without having to expend their cognitive resources.

The purpose of a recommendation system is to search for content that would be interesting to an individual. Moreover, it involves a number of factors to create personalized lists of useful and interesting content specific to each user/individual. Recommendation systems are Artificial Intelligence-based algorithms that skim through all possible options and create a customized list of items that are interesting and relevant to an individual. These results are based on their profile, search/browsing history, what other people with similar traits/demographics are watching, and how likely they are to consume the content.

## Types of Recommendation Systems

### 1. Content-Based

- **Definition:** Content-based systems use characteristic information to take item attributes into consideration.
- **Examples:** Twitter, YouTube.
- **Features Considered:** 
  - What music you are listening to.
  - What singer you are watching.
  - Embeddings for various features.
- **User Actions:** Recommending items based on user-specific actions or similar item recommendations.

Content-based systems make recommendations by creating a vector of item features. They hypothesize that if a user was interested in an item in the past, they will likely be interested in similar items in the future.

**Challenges:**
- These systems might make overly specialized recommendations, leading to a lack of diversity in the content suggested.

### 2. Collaborative Filtering

- **Definition:** Collaborative filtering systems are based on user-item interactions.
- **Mechanism:** 
  - Clustering users with similar ratings or similar preferences.
  - Recommending items based on a user's interaction history.
- **Examples:** Book recommendations, using clustering mechanisms.

Collaborative filtering operates on the assumption that if a user likes item A, and another user likes both item A and item B, then the first user might also like item B.

**Challenges:**
- Computationally expensive due to the need to calculate a large user-item matrix.
- Bias towards recommending only popular items.
- Difficulty in recommending new or less-known items.

### 3. Hybrid Systems

- **Definition:** Hybrid systems combine both content-based and collaborative filtering methods.
- **Mechanism:** 
  - Combining the strengths of both methods to avoid the weaknesses inherent in using just one approach.
  - Uses techniques like word2vec and embeddings.

Hybrid systems aim to provide more comprehensive and adaptable recommendations by leveraging both content and collaborative filtering approaches.


## Objective

This project implements a Book Recommendation System using a collaborative filtering approach with the Nearest Neighbors (NN) algorithm. The system recommends books based on user interactions, specifically by finding similarities between books in a user-item matrix. Given a book that a user likes, the system suggests other books that are similar, based on historical user preferences.

## Dataset

The dataset used in this project is a user-book interaction matrix that contains information about users' ratings of various books. This matrix is transformed into a form that the NN algorithm can use to compute similarities between books.

### Data Preprocessing

The preprocessing steps include:

1. **Loading the Data:** The raw data is loaded and inspected for missing or inconsistent values.
2. **Creating the User-Item Matrix:** This matrix is created where rows represent users and columns represent books. Each entry in the matrix indicates the rating a user has given to a book.
3. **Filling Missing Values:** Missing values in the matrix are filled using appropriate strategies to ensure the KNN model can be trained effectively.
4. **EDA:** Visualizing the distribution of features

## Features

- **User-Book Interaction Analysis:** Analyze and preprocess user interaction data to create a user-item matrix.
- **Nearest Neighbors Model:** Train a KNN model to compute similarities between books based on user ratings.
- **Book Recommendation:** Given a book, the system recommends similar books by querying the trained KNN model.
- **Model Persistence:** Save the trained model and other necessary data artifacts for later use.


## Model and Data Artifacts

### Model

- **Nearest Neighbors (KNN) Model**: This recommendation system uses a K-Nearest Neighbors (KNN) model to identify and recommend books similar to a user-specified book. The model calculates similarities between books based on user ratings and suggests the closest matches.

### Artifacts

1. **`model.pkl`**: Contains the trained KNN model, ready for making quick recommendations without retraining.
2. **`book_names.pkl`**: A list of book titles, used to map book IDs to their respective names during recommendations.
3. **`final_rating.pkl`**: The processed user-item rating matrix, essential for input into the model.
4. **`book_pivot.pkl`**: A pivoted version of the user-item matrix, optimized for efficient similarity calculations.

These artifacts ensure that the system can efficiently generate recommendations and be reused across different environments without repeating preprocessing or training.

## Model Evaluation

### Evaluation Approach

The effectiveness of the Nearest Neighbors (KNN) model is evaluated through qualitative assessment based on the relevance of the recommended books. After executing the recommendation function, the model provides a list of books similar to the user-specified input.

### Qualitative Evaluation

- **Relevance:** The recommended books are qualitatively checked for relevance to the input book. For example, recommending books from the same series (e.g., other "Harry Potter" books when the input is a "Harry Potter" title) indicates that the model is correctly identifying similar items.
- **User Experience:** The system's ability to avoid recommending the same book that the user searched for (as implemented in the function) enhances the user experience by providing diverse recommendations.

While the evaluation is primarily qualitative in this instance, the model demonstrates effectiveness in identifying and recommending books closely related to the user's interests. 

## Deployment
Deploy the model using a Streamlit app (app.py). The app allows users to input house data and get price predictions. To run the app, execute the following command:

https://book-recommendation-system-ml-cbuhkeure2vat6yw3qgvew.streamlit.app

## Future Work

### Potential Enhancements

 **Incorporate Additional Features:**
   - Integrate more features such as book genres, author information, and user demographics to improve recommendation accuracy.
  
 **Implement Quantitative Evaluation Metrics:**
   - Introduce metrics like precision, recall, and F1 score to quantitatively assess the model's performance.

 **Expand the Recommendation Algorithm:**
   - Experiment with other algorithms like matrix factorization, deep learning-based models, or hybrid systems to enhance recommendation quality.

 **Develop a User Interface:**
   - Build a web or mobile application to provide users with an intuitive and interactive platform for receiving book recommendations.

 **Address Cold-Start Problem:**
   - Implement strategies to handle new users or books with minimal interaction history, ensuring the system can still provide valuable recommendations.


