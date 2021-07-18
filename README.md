# Netflix-Recommandation-Sysytem

## 1.1 Problem Description
Netflix is all about connecting people to the movies they love. To help customers find those movies, they developed world-class movie recommendation system: CinematchSM. Its job is to predict whether someone will enjoy a movie based on how much they liked or disliked other movies. Netflix use those predictions to make personal movie recommendations based on each customer’s unique tastes. And while Cinematch is doing pretty well, it can always be made better.

Now there are a lot of interesting alternative approaches to how Cinematch works that netflix haven’t tried. Some are described in the literature, some aren’t. We’re curious whether any of these can beat Cinematch by making better predictions. Because, frankly, if there is a much better approach it could make a big difference to our customers and our business.

Credits: https://www.netflixprize.com/rules.html

## 1.2 Problem Statement
Netflix provided a lot of anonymous rating data, and a prediction accuracy bar that is 10% better than what Cinematch can do on the same training data set. (Accuracy is a measurement of how closely predicted ratings of movies match subsequent actual ratings.)

## 1.3 Sources
https://www.netflixprize.com/rules.html
https://www.kaggle.com/netflix-inc/netflix-prize-data
Netflix blog: https://medium.com/netflix-techblog/netflix-recommendations-beyond-the-5-stars-part-1-55838468f429 (very nice blog)
surprise library: http://surpriselib.com/ (we use many models from this library)
surprise library doc: http://surprise.readthedocs.io/en/stable/getting_started.html (we use many models from this library)
installing surprise: https://github.com/NicolasHug/Surprise#installation
Research paper: http://courses.ischool.berkeley.edu/i290-dm/s11/SECURE/a1-koren.pdf (most of our work was inspired by this paper)
SVD Decomposition : https://www.youtube.com/watch?v=P5mlg91as1c

## Objectives:

Predict the rating that a user would give to a movie that he ahs not yet rated.
Minimize the difference between predicted and actual rating (RMSE and MAPE)
## Constraints:

Some form of interpretability.

## Performance metric
Best Values comes from the SVD model
Mean Absolute Percentage 1.0726046873826458
Root Mean Square Error: 35.01953535988152


## Steps Involved
Surprise library has been used which is a python scikit building and anlayzing recommandation systems. This uses a collaborative filtering model. First the data is featurized for standard regression model and then the output of the model added with the previous feature is used to train the xgboost model. The surprise library consist of baseline models such as knn model with user-user similarity and knn model with item-item similarity.MatrixFactorisation is also usedsuch as SVD and SVD++ and the output is once again used as feature to train xgboost model.So, each of the surprise baseline model is trained and output of the feature is taken as the feature for training the xgboost model to give the final output and the performance matrix.


