# FindDefault-Prediction-of-Credit-Card-fraud

# Problem Statement
• A credit card is one of the most used financial products to make online purchases and payments. Though the Credit cards can be a convenient way to manage your finances, they can also be risky. Credit card fraud is the unauthorized use of someone else's credit card or credit card information to make purchases or withdraw cash.

• It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.

• The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

We have to build a classification model to predict whether a transaction is fraudulent or not.

During Development: In this phase, organize your project files in the following folder structure:
project-folder: Name this folder to reflect your project's name in all lowercase, using kebab casing with no spaces in the name.
1.	notebooks: This folder should contain Jupyter notebooks or Python scripts where you perform data exploration, preprocessing, feature engineering, and model building.
2.	data: This folder should contain the dataset(s) used in the project. Include both raw and processed data, along with a README file explaining the dataset's attributes.
3.	models: This folder should contain the trained machine learning models or statistical models used in the project. Include model serialization files (e.g., Pickle files) and any model artifacts.
4.	visuals: This folder should contain data visualizations and plots generated during exploratory data analysis or model evaluation. Visualizations should be saved as image files (e.g., PNG or JPEG).
5.	README.md: This Markdown file should include a detailed description of your project, problem statement, data sources, and explanations of your code and models. Also, provide instructions on how to run your code and reproduce the results.

# Data Exploration
To protect the user's identity and the security of their confidential information, the dataset provider has applied Principal Component Analysis transformation on the original numerical features and compressed it into 28 principal’s components.

Only two features have not been transformed i.e. 1) Time and 2) Amount

The feature class will be targeting column with user labels as:
0: non-fraudulent
1: fraudulent

The dataset exclusively comprises numerical features, and notably, there are no instances of missing values.

# Exploratory Data Analysis
For the subsequent step, we will conduct fundamental Exploratory Data Analysis (EDA) on the dataset to enhance our understanding and extract valuable insights.

The bar plot reveals a significant imbalance between classes (0: Non-Fraudulent) and (1: Fraudulent).

The majority of features are in PCA (Principal Component Analysis) form, with the exceptions being Time and Amount, a more in-depth examination of these two features is required.

# Now we will check the number of occurances of each class label and we will plot the information using matplotlib.

• We can see that our Non-Fraudulent transactions are over 99%.
• We will apply scaling techniques on the "Amount" feature to transform the range of values.
• We will drop the original "Amount" column and add a new column with the scaled values. We will also drop the "Time" columns as it is irrelevant.
• Now, we will split the credit card data with a split of 70-30 using train_test_split().
• train_test_split() function in scikit-learn is a useful utility for splitting a dataset into training and testing sets.

• Parameters
• X: Feature matrix
• Y: Target variable
• test_size: Proportion of the dataset to include in the test split. Here we have set the test_size as 0.3 means 30% of the data we take as testing data set.
• random_state: We have set the seed for random number generation, to ensure the reproducibility.

# Applying Machine Learning Algorithm to Credit Card Dataset
• We will explore various machine learning algorithms to find the most effective model for our binary classification problem.
• The task involves predicting one of the two class labels. We plan to access the performance of different algorithms, such as Random Forest and Decision Tree, to identify the most suitable solution for our specific problem.

Here, We understand the confusion matrix for the random forest as well as for the decision tree.

Class-Imbalance
• The Random Forest classifier has slightly a better result over the Decision Tree Classifier.
• In a class Imbalance issue, where genuine transactions account for over 99% of the dataset and credit card fraud transactions constitute only 0.17%.
• Training the model without addressing the imbalance can lead to biased predictions.
• Despite the apparent accuracy, such a model may not effectively capture the nuances of the minority class (fraud transactions) and may not generalize well to real-world situations.
• The class imbalance problem can be solved by various techniques. Oversampling is one of them.

# We will use the SMOT (Synthetic Minority Oversampling Technique, or SMOTE).
It is the method of data augmentation for the minority class.

We can see that our model performed much better than the previous Random Forest classifier without oversampling.
We have applied the techniques to address the class imbalance issues and achieved an accuracy of more than 99%

# We will import the pickle for dumping the dataframe and the model for future deployment.








