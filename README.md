# Fraud Detection

**Introduction:**
Fraud detection is the identification and prevention of unauthorised monetary transactions. It is import for security management and to stop financial and reputational damage. Fraud has become more frequent and has cost companies to lose billions of dollars annually in the financial industry. Fraud detection works by using a variety of applications and methods to prevent fraudulent activities by detecting them through various factors. The effectiveness of fraud detection depends on the quality of data, the quantity of data and configuration of algorithms. In this dataset we investigate an imbalanced dataset and the most effective algorithm to use to determine fraudulent and non-fraudulent transaction activity.

**Aim/Objective:**
The aim of this study is to effectively determine which factors contribute and indicate to fraudulent transactional activities, find the most effective machine learning algorithms and techniques for the Trust Bank dataset, whilst tackling the imbalance challenges of the dataset

**Methods:**
Data Exploration and Pre-Processing:
During the data exploration analysis phase, the dataset was examined. The dataset had 590540 rows and 138 columns with a mixture of categorical and numerical data. 131 of those columns contained missing values, which account for around 52% of the dataset and indicated high missingness in many columns. The missingness in the columns (features) were handled using imputation techniques which was important for model performance. Categorical features with missingness were imputed using mode imputation, numerical columns were handled using mean imputation.

After imputation, the categorical features were one-hot encoded, and the numerical features were label encoded. Once features were encoded, the numerical features were scaled. Scaling is a critical process before model building.

The distribution of fraud was investigated and found to be imbalanced. This needed to be addressed so the model doesn't over-fit and assume there are more non-fraud transactions but rather detect the patterns for the categories of classification. This was resolved using SMOTE techniques which oversample the underrepresented class with synthetic values from the existing class examples, while preserving information. 

Furthermore, the banks region-rating and products were investigated alongside the classification of fraud and non-fraud transactions to examine whether certain regions and products had more prevalent fraudulent activity.

Features were used for the model based on highest mean from correlation with the classification of fraud and non-fraudulent transactions. This was performed using a correlation matrix output.

**Model building:**
A Random Forest  algorithm was tested for the data using the K best score which uses a  univariate statistical test for features with mutual information. This was performed to select features that are individually most relevant to the target variable that would be most useful for the Random Forest model. Additionally, this was run with SMOTE technique.
A Linear regression algorithm was also tested for the Trust Bank dataset after data pre-processing and feature engineering. This was run with SMOTE technique to better handle the imbalance in the data classes of Fraud.

**Results:**
Random Forest Model:
The random Forest model returned an overall accuracy of 0.93 and balanced trade-off.  For non-fraudulent activities, the model accurately determined 0.92 true positive instances correctly, leaving only 0.08 false positives. With a recall of 0.93, only 0.7 true positive instances were not identified correctly  by the model. This resulted in an overall f1 score of 0.93. For fraudulent activities, the model accurately determined 0.93 true positive instances correctly, leaving only 0.7 false positives. With a recall of 0.92, only 0.08 were not identified correctly  by the model. This resulted in an overall f1score of 0.92. In addition, a max tree depth test was performed and indicated that the effective max tree depth to use before the model starts to overfits the data was 15.

Linear Regression Model:
The Linear Regression model returned an overall accuracy of 0.87 and balanced trade-off.  For non-fraudulent activities, the model accurately determined 0.88 true positive instances correctly, leaving 0.12 false positives. With a recall of 0.87, a high majority of true positive instances were identified effectively by the model. This resulted in an overall f1 score of 0.87. For fraudulent activities, the model accurately determined 0.87 true positive instances correctly, leaving only 0.13 false positives. With a recall of 0.88, a high majority of true positive instances were identified effectively by the model. This resulted in an overall f1score of 0.88. A learning curve was plotted to illustrate how much the model changes as the amount of training data increases which showed around 600 was the model’s peak.

**Conclusion:**
The best performing model was the Random Forest model, which used a KBest score to select features most relevant features in relation to the target, and SMOTE techniques to handle the imbalanced dataset. Generally, Random Forest models are known for their high accuracy, and compared to decision tree models. They aggregate multiple tree predictions to obtain the highest possible accurate and stable result without overfitting data, creating a more generalized model. It is an effective model to use for imbalanced data as it is less sensitive to outliers and can handle both numerical and categorical data, without needing extensive pre-processing, proving to be versatile. However, Random forest are not well suited for linear relationships and can favour majority classes in imbalanced datasets, which is why SMOTE method was accompanied with the model. They can also require significant computing and processing power, especially for large datasets. To end, Random Forest models can also be complex which is at disadvantage for crucial interpretability.

