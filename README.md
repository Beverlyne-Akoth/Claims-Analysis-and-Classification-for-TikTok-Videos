# Project Title: Claims Analysis and Classification for TikTok Videos

# Project Description
Using Python and Python libraries for data science to predict whether TikTok videos contained claims or opinions to improve the triaging process of videos for human review 

# Project Overview
The objective of the project is to create a model to analyse claims submitted by TikTok users on videos and to ascertain whether the video contains a claim or offers an opinion.
The data used was a CSV file that included video details such as the video's length, text transcription, number of likes, downloads, comments, and shares, as well as video creator details, including verification status, and other relevant fields.
To accomplish the task, EDA was done on the data, and later on, different machine learning models were fit to the data. The models used were RandomForest and XGBoost.
The best parameters for the RF model were;
{'max_depth': None,
 'max_features': 0.6,
 'max_samples': 0.7,
 'min_samples_leaf': 1,
 'min_samples_split': 2,
 'n_estimators': 100}

The best parameters for the XGBoost model were;
{'learning_rate': 0.1,
 'max_depth': 4,
 'min_child_weight': 3,
 'n_estimators': 500}

Both models performed extremely well with a recall of 1.00. The figure below shows the classification report for the two models.
* RF
                  precision recall  f1-score   support

     opinion       1.00      1.00      1.00      1895
       claim       1.00      1.00      1.00      1922

    accuracy                           1.00      3817
   macro avg       1.00      1.00      1.00      3817
weighted avg       1.00      1.00      1.00      3817

* XGBOOST
                   precision recall    f1-score   support

     opinion       0.99      1.00      1.00      1895
       claim       1.00      0.99      1.00      1922

    accuracy                           1.00      3817
   macro avg       1.00      1.00      1.00      3817
weighted avg       1.00      1.00      1.00      3817

The Confusion Matrix, however, revealed that the Random Forest model had a total of 9 false negatives (claims that the model misclassified as opinions) while the XGBoost model had 18 false negatives.
Since identifying claims was the priority, it's important that the model be good at capturing all actual claim videos. The random forest model, therefore, had better scores and is the champion model.

In conclusion;
* The model performed extremely well on both the validation and test holdout data. Furthermore, both precision and F1 scores were consistently high (1.00). The model successfully classified claims and opinions.
* The model's most predictive features were all related to the user engagement levels associated with each video. The model was classifying videos based on how many views, likes, shares, and downloads they received.
* Because the model currently performs nearly perfectly, there is no need to engineer any new features.
* The current version of the model does not need any new features. However, it would be helpful to have the number of times the video was reported. It would also be useful to have the total number of user reports for all videos posted by each author.
