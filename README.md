# YouTube_Analysis

### Notebook for HackLive 2 Analytics Vidhya Hackathon.

## Private Leaderboard Rank 3

![](./Rank3.png)

## Feature Enginnering

### What Worked and What Didn't?

* Vanilla numerical features like views, comment count and dislikes were highly correlated with the target feature i.e number of likes in the video.

* Date of publish of the video was an important feature.

* Label Encoding of categorical columns like country code, channel title and category id worked out well.

* Aggregating features and transforming them gave better outcomes than using vanilla features.

* Using transformed min, max, mean and sum features and grouping them with channel title gave decent performance.


 * Textual features were taken into account by calculating the length of the title, tags used and description with importance of features ranked in the same order.

 * Interestingly by performing EDA one could infer that longer the title length lesser would be the number of likes recieved on the video.

 * Grouping seasonality features(month and day of week) along with dislikes, views and comment count helped a tad bit but weren't exceptional features.

 * Top N words were taken into account using count vectorizer on title, tags and description and added icing to the cake.

* Giving polarity scores to the textual features(not tried) like title, tags and description using VADER might have helped in determining whether a particular sentiment had more influence on the number of likes.

## Modelling

* The three boosting algorithms tried are LGBMRegressor, XGBoostRegressor and CatBoostRegressor.

* Amongst the three, LGBMRegressor outshone the others in terms of root mean squared log error which was the evaluation metric in this hack. As expected LGBMRegressor was also faster than XGB and Catboost.

* Tried ensembling LGBM with XGBoost but the performance suffered slightly so using LGBM individually was more fruitful.

* Lastly performed a random search to find the best hyperparameters which gave a boost on the leaderboard at the eleventh hour. If time had permitted, grid search would have possibly worked better and is a recommendation to try.
