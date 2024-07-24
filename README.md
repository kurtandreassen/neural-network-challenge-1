# neural-network-challenge-1
Module 18  neural-network-challenge-1

Purpose of this project is to Neural Network to analyze student loan data to predict n student loan refinancing. If the company can predict whether a borrower will repay their loan, it can provide a more accurate interest rate for the borrower. and predict loan payback by the student.

Developed in Google Colab, the following are required:

# Imports
import pandas as pd
import tensorflow as tf
from tensorflow.keras.layers import Dense
from tensorflow.keras.models import Sequential
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.metrics import classification_report
from pathlib import Path

Determination of predctions following the following steps:
1. Prepare the data to be used on a neural network model, data source: https://static.bc-edx.com/ai/ail-v-1-0/m18/lms/datasets/student-loans.csv
2: Using the preprocessed data, create the features (X) and target (y) datasets. The target dataset should be defined by the preprocessed DataFrame column “credit_ranking”. The remaining columns should define the features dataset.
3: Split the features and target sets into training and testing datasets:
    X_train, X_test, y_train, y_test = train_test_split(x, y, random_state=1
4: Use scikit-learn's StandardScaler to scale the features data.
5. Compile and Evaluate a Model Using a Neural Network
5.1: Create a deep neural network by assigning the number of input features, the number of layers, and the number of neurons on each layer using Tensorflow’s Keras.
5.2: Compile and fit the model using the binary_crossentropy loss function, the adam optimizer, and the accuracy evaluation metric.
5.3: Evaluate the model using the test data to determine the model’s loss and accuracy.
5.4: Save and export your model to a keras file, and name the file student_loans.keras.
6: Predict Loan Repayment Success by Using your Neural Network Model
6.1: Reload your saved model
6.2: Make predictions on the testing data and save the predictions to a DataFrame.
6.: Display a classification report with the y test data and predictions.


Project responses:

1. Describe the data that you would need to collect to build a recommendation system to recommend student loan options for students. Explain why this data would be relevant and appropriate.

1.1 Student Demographics, possibly Age, gender, and marital status to helpin understanding the student's background and potentially their financial independence or reliance on family support.

1.2 Academic Information such as type of degree (undergraduate, graduate), institution type (public, private, community college), and academic performance. to determine costs (loan amount) and potential future earnings, which can influence loan options.

1.3 Current Student's Financial Status such as Income, employment status, and existing debts. for assessing the student's histor & ability to repay loans.

1.4 Financial Aid Received suchScholarships, grants, and previously taken student loans. This information is necessary to calculate the remaining financial need.

1.5 Future expected salary after graduation, based on field of study and academic performance. This helps in recommending loans that the student can realistically repay based on their potential earnings.

1.6 Historical Data on Loan Performance such as default rates, average repayment times, and satisfaction scores for different loan options. This can help in recommending loans that have a good track record.

1.7 This additional data is relevant and appropriate because it allows the recommendation system to consider a comprehensive view of the student's financial situation, academic background, and future potential. By analyzing this information, the system can recommend loan options that are affordable, suitable for the student's financial and academic profile, and aligned with their preferences and future earning potential.

2. Based on the data you chose to use in this recommendation system, would your model be using collaborative filtering, content-based filtering, or context-based filtering? Justify why the data you selected would be suitable for your choice of filtering method.

2.1 The model would primarily use ontent-based filtering. This decision is based on the nature of the data collected, which includes detailed information about the students (demographics, academic information, financial status, loan preferences, and future earnings potential) and the characteristics of different loan options.

2.2 Justification for Content-Based Filtering:

2.2.1. Personalized Recommendation based on data which includes detailed individual profiles, such as academic performance, financial need, and future earnings potential. Content-based filtering can leverage this information to recommend loan options that closely match the student's specific circumstances and preferences.

2.2.2. Direct Attributes Matching as the system can analyze the attributes of loan options such as interest rates, repayment terms and match them with the student's preferences and financial capability. This direct matching of content (loan attributes) with user preferences (student's financial and academic profile) is the essence of content-based filtering.

2.2.3 Focus on Item Features, the recommendation is based on the features of the loans themselves, such as the type of loan, interest rates, and terms of repayment, which can be directly compared to the student's needs and future earning potential. This approach aligns well with content-based filtering, which recommends items based on their features and how these features match the user's profile.

In summary, the detailed, attribute-rich data collected for this recommendation system lends itself well to content-based filtering, where recommendations are made by matching the specific needs and preferences of the student with the characteristics of various loan options. This method allows for personalized, relevant, and effective loan recommendations for each student.

3. Describe two real-world challenges that you would take into consideration while building a recommendation system for student loans. Explain why these challenges would be of concern for a student loan recommendation system.