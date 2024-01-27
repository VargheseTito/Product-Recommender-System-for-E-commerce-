# Product-Recommender-System-for-E-commerce-
Drive Link to download the source dataset- https://drive.google.com/drive/folders/1rPayt8XENGSMNn6XOXvlUIUj1YBNESzL?usp=drive_link

Design and implement a personalized product recommendation system for an e-commerce platform.
Objective: Enhance user experience through personalized suggestions using collaborative filtering or other relevant approaches
Importance of Personalized Recommendations

![image](https://github.com/VargheseTito/Product-Recommender-System-for-E-commerce-/assets/110298267/537e392a-5eba-445b-9b8f-c0ec9c5a22ab)


Enhancing User Experience:

Tailoring product suggestions to individual preferences increases user satisfaction.  

Provides a more enjoyable and relevant shopping experience.

Boosts engagement by aligning with unique customer tastes and needs.

Increasing Sales:

Personalized recommendations lead to higher conversion rates.

Encourages additional purchases by showcasing relevant items.

Improves overall customer loyalty and lifetime value.

ALgorithm Overall Flow

Data Ingestion:

Acquire fine foods dataset from Amazon, encompassing product reviews and user interactions.
Exploratory Data Analysis (EDA):
Conduct thorough EDA to gain insights into data distribution, user behavior, and product popularity.
Visualize key statistics, including rating distributions, user engagement patterns, and product review frequencies.

Data Preprocessing:
Handle sparsity by filtering out data based on user and product review frequency.
Apply the assumption: Genuine users have provided reviews more than 100 times.
Apply the assumption: Products require a minimum of 2 reviews for inclusion.

Matrix Factorization:
Implement Singular Value Decomposition (SVD) and Non-Negative Matrix Factorization (NMF) algorithms.
Decompose user-item interaction matrix to identify latent factors for personalized recommendations.

Collaborative Filtering:
Apply KNN with Pearson Baseline similarity for capturing user preferences.
Utilize collaborative filtering to enhance recommendations based on user behavior.

Handling Sparsity:
Filtering users and products based on review frequency ensures relevance and reduces sparsity.
Applying assumptions narrows down the dataset, focusing on prolific users and well-reviewed products


Inferences:
The dataset consists of 5,68,454 entries and 10 columns. Here is a brief overview of each column:

Id: This is an int data type column that contains the row id/index number for amazon fine food reviews. Each row id number can represent unique id.

ProductId: An object data type column representing the product code for each item.

UserID: An Object column that contains the user ID for each amazon fine food reviews.

ProfileName: This column, also an object data type, contains name of the User/Reviewer. It has some missing values, with 5,68,438 non-null entries out of 5,68,454 (16 null values).

HelpfulnessNumerator: This is an integer column indicating the number of users who found the review helpful.

HelpfulnessDenominator: This is an integer column indicating the number of users who indicated whether they found the review helpful or not (how many people reviewed).

Score: An integer column representing the rating of each product.

Time: An integer column representing the timestamp of the review.

Summary: An object column recording the brief summary of the review took place.This column does not has a significant number of missing values, 5,68,427 non-null entries out of 5,68,454 (27 null values).

Text: An object column recording the whole text of the review.

From a preliminary overview, it seems that there are missing values in the ProfileName and Summary columns which need to be addressed. The Time column is in int format which has to converted into datetime format, which will facilitate further time series analysis. We also observe that a single user can have multiple reviews as inferred from the repeated UserID in the initial rows.

The next steps would include deeper data cleaning and preprocessing to handle missing values, potentially erroneous data, and to create new features that can help in achieving the project goals.

Data includes:

Reviews from Oct 1999 - Oct 2012

568,454 reviews

256,059 users

74,258 products

260 users with > 50 reviews

Inferences:

UserID:

There are 2,56,059 unique Users/reviewers reviewing different products.

The most active user is A3OXHLG6DIBRW8, appearing 448 times in the dataset.

ProfileName:

There are 2,18,416 unique ProductName representing different User profiles.

The most frequent stock code is C. F. Hill "CFH", appearing 451 times in the dataset.

ProductId:

There are 74,258 unique ProductId representing different products.

The most frequent stock code is B007JFMH8M, appearing 913 times in the dataset.

Summary:

The most frequently used word to breifly summarize a food review was "Delicious!", it has been used for 2462 times by the users.

There are some missing values in this column which need to be treated.

Text:

There are 3,93,579 unique food reviews.

The most frequent food reviews is "This review will make me sound really stupid,", appearing 199 times.

Id:

There are 5,68,454 unique row id numbers, indicating 5,68,454 separate reviews.

Score:

The average rating of food reviewsis approximately 4.1.

The rating score has a range, with a minimum value of 1 and a maximum value of 5.

The standard deviation is quite normal, not indicating a significant spread in the data.

We will train several algorithms to compare their performance to get us the best working model. We will be using:

Item Based Collaborative Filtering, with Cosine, Pearson, and Euclidean Distance for similarity score.

Single Value Decomposition aka SVD

Non Matrix Factorization aka NMF


![image](https://github.com/VargheseTito/Product-Recommender-System-for-E-commerce-/assets/110298267/04619b8d-0bcf-4e1b-84c5-37a65d1569bf)


We will evaluate how each model performs and select the best working model for our recommender system.

Recommender systems have a problem known as user cold-start, in which it is hard to provide personalized recommendations for users with none or a very few number of consumed items, due to the lack of information to model their preferences.

For this reason, we are keeping in the dataset only users with at least 5 interactions.

Assumptions

We will consider only those UserIds/ Reviewers as geniune users , who have atleast provided reviews/ ratings more than 100 times.

We will consider only those ProductsIds for buliding recommedation system, where the minimum number of atleast 2 reviews required per ProductId

For the sake of similarity and to run the model quickly we will only consider users who have rated more than 100 times and products that were rated more than 2 times. Once we build our code structure and understand the flow we can run the same on the entire dataset.
