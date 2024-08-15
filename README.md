# Book Recommendation System

![Book Recommendation System](https://img.shields.io/badge/Recommendation%20System-Book-brightgreen)

## Table of Contents

- [Overview](#overview)
- [Objective](#objective)
- [Dataset](#dataset)
- [Features](#features)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [How to Run](#how-to-run)
- [Detailed Explanation of the Notebook](#detailed-explanation-of-the-notebook)
- [Model and Data Artifacts](#model-and-data-artifacts)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)



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

## Installation

### Prerequisites

Ensure that you have the following installed:

- Python 3.6 or higher
- Jupyter Notebook

### Step-by-Step Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/Book_Recommendation_System.git
   cd Book_Recommendation_System
