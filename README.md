# Project Title: Claims Analysis and Classification for TikTok Videos

# Project Description
Using Python and Python libraries for data science to predict whether TikTok videos contained claims or opinions to improve the triaging process of videos for human review 

# Project Overview
The objective of the project was to analyse claims submitted by TikTok users on videos and to ascertain whether the video presented contains a claim or offers an opinion.
The data used contained video details such as the length of the video, text transcription, number of likes, downloads, comments, and shares on the video, video creator details, including verification status, and such other fields.
To accomplish the task, EDA was done on the data and later on different machine learning models fit to the data to predict whether the video was a claim or an opinion. The models used were RandomForest and XGBoost.
Both models performed extremely well with a recall of 1.00. However, the XGBoost errors tended to be false negatives. Identifying claims was the priority, so it's important that the model be good at capturing all actual claim videos. The random forest model has a better scores, and is therefore the champion model.

In conclusion;
* I can recommend this model because it performed well on both the validation and test holdout data. Furthermore, both precision and F1 scores were consistently high. The model very successfully classified claims and opinions.
* The model's most predictive features were all related to the user engagement levels associated with each video. It was classifying videos based on how many views, likes, shares, and downloads they received.
* Because the model currently performs nearly perfectly, there is no need to engineer any new features.
* The current version of the model does not need any new features. However, it would be helpful to have the number of times the video was reported. It would also be useful to have the total number of user reports for all videos posted by each author.
