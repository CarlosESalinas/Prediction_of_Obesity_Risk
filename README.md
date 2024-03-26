![Obesidad](obesity.png)

# Multi-Class Prediction of Obesity Risk

This repository showcases my work for the Kaggle competition S04E02, focusing on Multi-Class Prediction of Obesity Risk. 
The goal of this competition was to use various factors to predict obesity risk in individuals, which is related to cardiovascular disease.


### About Dataset

The data consist of the estimation of obesity levels in people from the countries of Mexico, Peru and Colombia, with ages between 14 and 61 and diverse eating habits and physical condition , data was collected using a web platform with a survey where anonymous users answered each question, then the information was processed obtaining 17 attributes and 2111 records.
The attributes related with eating habits are: Frequent consumption of high caloric food (FAVC), Frequency of consumption of vegetables (FCVC), Number of main meals (NCP), Consumption of food between meals (CAEC), Consumption of water daily (CH20), and Consumption of alcohol (CALC). The attributes related with the physical condition are: Calories consumption monitoring (SCC), Physical activity frequency (FAF), Time using technology devices (TUE), Transportation used (MTRANS). You can know more about the dataset in this [link](https://www.kaggle.com/datasets/aravindpcoder/obesity-or-cvd-risk-classifyregressorcluster)

## Explanation of the main function

The main function for this project is named `get_best_model`, which is designed to assist in finding the best model and its corresponding parameters for a given dataset. This function works with two classifiers: Random Forest and Support Vector Machine (SVC).

To find the best hyperparameters, I used the GridSearchCV method. This is a technique for hyperparameter tuning, a crucial step in creating machine learning models. Hyperparameters are configurations that are not learned from the data but are set before training. They significantly affect the model's performance. GridSearchCV exhaustively searches through a specified parameter grid to find the best combination of hyperparameters for a given model. It evaluates each combination using cross-validation, which helps prevent overfitting.

As for the classifiers used, they are SVC and Random Forest. SVC is a supervised learning algorithm used for classification tasks. It works by finding the optimal hyperplane that separates different classes in the feature space. It has several hyperparameters such as the choice of kernel (linear, polynomial, radial basis function, etc.), regularization parameter (C), and kernel-specific parameters. On the other hand, Random Forest is an ensemble learning method useful for classification and regression tasks. This model constructs multiple decision trees during training and generates the mode (for classification) or the average prediction (for regression) of the individual trees. The model has hyperparameters such as the number of trees in the forest, maximum depth of the trees, and minimum samples required to split a node.

Finally, the `get_best_model` function, after fitting GridSearchCV for both SVC and Random Forest, compares the best scores obtained by each model. The best score represents the model's performance on the validation data during cross-validation. It then selects the model with the highest best score as the `best_model`.

By using this function, the goal is to efficiently search for the best model and its hyperparameters without manually trying out different combinations, thus saving time and effort in the model development process.


## The best Model 

The best model was Random Forest with the next accuracy and paramenters:

The Best Score for the best model was: 0.896 

The Best Parameters for the best model were: 
                                           Best Parameters
randomforestclassifier__bootstrap                   False
randomforestclassifier__max_depth                      20
randomforestclassifier__min_samples_leaf                1
randomforestclassifier__min_samples_split              10
randomforestclassifier__n_estimators                  300