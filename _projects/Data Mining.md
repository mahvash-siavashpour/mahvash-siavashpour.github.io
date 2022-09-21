---
layout: page
title: Data Mining Course Projects
description: 5 mini projects in data mining
img: assets/img/data-mining.png
importance: 1
category: AI
---
There 5 different project here that each cover a different section in the data mining world; from preprocessing and analyzing data to classification, clustering, etc.
## Project List
- [Analysing Iris Dataset](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/tree/main/AnalyseIrisDataset)
- [Classification](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/tree/main/AssociationRuleExtraction)
- [Clustering](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/tree/main/Classification)
- [Association Rule Extraction](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/tree/main/Clustering)
- [Diabetes Detection](https://github.com/mahvash-siavashpour/Data-Mining-Excercise/tree/main/Diabetes-Detection)

## Project Description
A series of different data mining sub-projects are implemented in this project. This project was implemented to practice using different libraries and to work with different algorithms to gain knowledge and experience in this field of science. The full explanation of each sub-projects is written in the following sections.

### Analysing Iris Dataset
This project aimed at preprocessing the data obtained from the Iris dataset using two major preprocessing libraries in machine learning: [Pandas](https://pandas.pydata.org/docs/), and [scikit-learn](https://scikit-learn.org/stable/). <br>
The Iris dataset contains information on three types of flowers (iris-setosa، iris-versicolor, iris-virginica). The data collected for each of these categories of data contains four columns named: <br>
- sepal length in cm <br>
- sepal width in cm <br>
- petal length in cm <br>
- petal width in cm <br>

For preprocessing purposes, the missing values were deleted from the dataset. Also, the non-numeric (categorical) data was encoded using label encoding. Although label encoding is a very suitable approach to solving this problem, it can only be applied to ordered data. In the case of encoding data with no order, one hot encoding is a feasible method.<br> 
Normalization eas also done on this dataset in order to get better results in training phase. <br>
Visualizing the data before applying any ml algorithm can help understand and analyze data better. Visualizing data with more than three dimensions is not feasible nor easy. To address this problem, PCA was applied to this data to obtain a 2 dimensional dataset for visualizing purposes.<br>

### Classification
The main goal of this project was to practice using and finding the best classification algorithms and functions for each type of data distribution. Different parameters were analyzed during this project, including learning_rate, to obtain the best results and accuracy. <br>
In the last section of this project, the fashion_mnist dataset was imported to test the classification algorithm.

### Clustering

### Association Rule Extraction

### Diabetes Detection
In this project a Diabetes detection model has been constructed using XGBoost or Extreme Gradient Boost, which is an open source library used for parallel tree boosting. After construnction the model, it is trained on the information of more than 70,000 patients through the questionnaire that they filled out for the Organization for Disease Control and Prevention.

#### Dataset
The data used in this project is the information of more than 70,000 patients through the questionnaire that they filled out for the Organization for Disease Control and Prevention. The dataset contains 22 columns as described bellow:
- HighBP: High Blood Pressure
- High Cholesterol
- Cholesterol Check: Whether the patient has done a cholesterol check
- BMI: Body Mass Index
- Smoker
- Stroke
- HeartDiseaseorAttack
- Physical Activity
- Fruits
- Veggies
- Heavy Alcohol Consumption
- Any Health Care
- No Doctor because of Cost: Whether the patient posponed or canceled a doctor's appointment due to the costs
- General Health
- Mental Health
- Physical Health
- Difficulty Walking
- Sex: Gender
- Age
- Education
- Income

#### Preprocessing
Before doing any training, a series of preprocessing has been done on the data. 
1. **NULL Values:** <br>
  First I found all null values and then replace them by either the mean(numerical) or the mode(categorical and binary) of that column.
  By doing so we can keep and refine the dataset with out removing any data.
2. **Unifying White Spaces:** <br>
  After finding all white spaces in the column names of data, I replaced them with a "-" making the names Kebab Case.
3. **Normalizing:** <br>
  Different feature have different ranges of values. Scaling them into a specific range helps a lot with in the training of the model.
5. **Categorical Features:** <br>
  Some features are categorical and for us to be able to use them in numerical formats I changed them into numerical vectors using one-hot-encoding.
  
#### XGBoost Model
XGBoost is an open-source software library which provides a regularizing gradient boosting framework for C++, Java, Python, R, Julia, Perl, and Scala. It works on Linux, Windows, and macOS. From the project description, it aims to provide a "Scalable, Portable and Distributed Gradient Boosting Library".([Wikipedia](https://en.wikipedia.org/wiki/XGBoost)) <br>
In this phase of the project I created an XGBClassifier with the parameters specified bellow: <br>
```
model = XGBClassifier(
            tree_method='gpu_hist',
            Learning_rate=0.1,
            Max_depth=4,
            N_estimator=200,
            Subsample=0.5,
            Colsample_bytree=1,
            Random_seed=123,
            Eval_metric='auc',
            Verbosity=1)
```
And then trained the model. The results after the training are available in the notebook.
#### Hyperparameter Tuninning
There are many parameters that can affect the model. In order to find the best parameters for our model we use GridSearchCV to do a cross-validation constructiong the model with different combinations of the parameters and then scoring them. The candidate lists of the parameters are shown bellow:
```
learning_rate_list = [0.02, 0.05, 0.1, 0.3] 
max_depth_list = [2, 3, 4] 
n_estimators_list = [100, 200, 300] 
colsample_bytree = [0.8, 1]
```
