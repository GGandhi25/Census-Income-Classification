# Census-Income-Classification
Implementing KNN and Logistic Regression from scratch on Census Income Dataset
IN6227 Data Mining – Assignment 1 Variant 1

Introduction
For this assignment, the K-Nearest Neighbors (KNN) algorithm was implemented for classification purposes. The Census Income dataset from the UCI Machine Learning Repository was used, which consisted of information on individuals including their demographic features such as age, education, occupation, and marital status, as well as their income level, categorized as either ">50K" or "<=50K".

Exploratory Data Analysis 
EDA was conducted on the Census Income dataset before implementing the k-NN algorithm. The dataset contained 32,561 instances and 15 features, including the target feature "income". A mix of categorical and numerical variables were included in the features. 
During the EDA phase, several observations were made about the Census Income dataset. These included:
• The feature "Age" follows a normal distribution, which suggests that most individuals in the dataset are within a certain age range.
• The features "Capital-gain" and "Capital-loss" are highly skewed, indicating that most individuals have low capital gains or losses, but there are a few extreme outliers.
• The feature "Native-country" may not be a useful predictor of income level, as it may be redundant compared to other features.
• The features "Education" and "Education-num" are highly correlated, indicating that they provide similar information about an individual's level of education.
• There is class imbalance in the target variable, with a significantly larger number of instances belonging to the "income <=50K" class than the "income >50K" class.

Pre-processing
The first step involved checking for missing values in the dataset ( ‘?’ values). These were handled by using the argmax function, for columns workclass, occupation, and native-country, to find the most common value in each categorical feature, and then replacing the missing values with those values. This was done in order to protect the data's validity and avoid biases from being introduced if the missing values had been ignored.
The target variable, "income," was then converted to a binary variable with ">50K" mapped to 1 and "<=50K" mapped to 0 using the map function. The categorical features were then converted to numerical values using LabelEncoder from the scikit-learn library. Finally, the numerical features were standardized using the StandardScaler from Scikit-learn to bring them to a common scale and avoid any bias in the algorithm towards features with larger values. The dataset was split into training and testing sets using a 70/30 split, with 70% of the data used for training and 30% for testing.

Model Training and Evaluation
The census dataset was split into training and testing sets using a 70/30 split ratio. This split was appropriate to ensure that the model was trained on a sufficiently large dataset while also having enough instances in the testing set to evaluate its performance. 
The KNN algorithm was used to fit the model on the training set. KNN is a simple yet powerful algorithm that is commonly used for classification tasks. It was a prudent choice because it is effective with datasets that contain many features, including numeric ones. The census dataset includes numerous continuous numeric features such as age, hours per week, and capital gains, making it well-suited for use with KNN. In addition, the KNN algorithm does not make any assumptions about the distribution of the data, which allows it to perform well on datasets with complex distributions. 
The Euclidean distance was chosen as the similarity metric to measure the distance between two instances in the dataset. This distance metric was appropriate for the dataset because it is a general-purpose distance metric that works well with continuous numeric features, which the dataset contains. Additionally, the Euclidean distance was well-understood, easy to compute, and interpret.
K was set to 5 in the KNN algorithm. This value was chosen based on experimentation and cross-validation. 
To evaluate the performance of the model, four performance metrics - accuracy, precision, recall, and F1 score - were calculated. These metrics were chosen because they provide an overall picture of the model's performance. Accuracy measured the proportion of correct predictions, precision measured the proportion of true positives among predicted positives, recall measured the proportion of true positives among actual positives, and F1 score was calculated as the harmonic mean of precision and recall. These metrics were used to assess the performance of the model on the test data.
After training the model on the training data and evaluating its performance on the test data, the following results were obtained:
• Accuracy: 0.815 
• Precision: 0.638 
• Recall: 0.549 
• F1 Score: 0.590
These results indicated that the model performed well on the test data, achieving a relatively high accuracy and F1 score. However, the precision and recall values suggested that there may be room for improvement in the model's ability to correctly identify positive cases.
To compare the performance of the KNN from scratch model and the scikit-learn KNN model, both models were trained on the training data and their performance was evaluated on the test data. The accuracy values for both KNN models were very similar. While this difference is small, it is interesting to note that the scikit-learn implementation performed slightly better than the KNN model implemented from scratch.

Conclusion
In summary, the implementation of the KNN algorithm for classification on the Census Income dataset was a success. The model exhibited strong performance on the test data, though there was some room for improvement in its ability to accurately identify positive cases. Nonetheless, the KNN algorithm's simplicity and effectiveness make it a valuable tool for a variety of machine learning applications. Overall, this project demonstrates the potential of the KNN algorithm for classification tasks and highlights the importance of careful analysis and evaluation of machine learning models.
 
![image](https://user-images.githubusercontent.com/122602469/224449091-627dd8fa-8ddc-49e9-994d-eec0e11cc6d0.png)
