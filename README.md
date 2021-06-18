# REK - Project 1

## Table of contents
* [Project description](#project-description)
* [Installing](#installing)
* [Requirements](#requirements)
* [Scores](#scores)

## Project description
Recommender for the hotel reservation. The goal was to achieve the best HR@10 in the final evaluation.

Final solution uses:
* SVRCBUIRecommender
* One-hot encoding for items and users
* Updated filter ```filter_out_long_stays``` to ```<= 14```

HTML versions of jupyter notebook are in ```html``` catalog.

## Installing
Linux or Mac (in project catalog):
```
conda create --name rekProjectOne --file requirements.txt python=3.6
source activate rekProjectOne
```

Windows (in project catalog):
```
conda create --name rekProjectOne --file requirements.txt python=3.6 
activate rekProjectOne
```

In project catalog:
```
jupyter notebook
```

Notebooks run in the following order: 
1. ```project_1_data_preparation.ipynb```
2. ```project_1_recommender_and_evaluation.ipynb```

In  ```project_1_recommender_and_evaluation.ipynb``` run all cells except second, third, and fourth tuning.

## Requirements
* pandas >= 1.2 (the most important)
* numpy >= 1.20.2
* matplotlib >= 3.3.4
* seaborn >= 0.11.1
* copy
* random
* itertools
* hyperopt >= 0.2.5
* IPython >= 7.22.0
* collections
* os
* scikit-learn >= 0.24.2
* traceback >= 1.7.0

Details for anaconda are in ```requirements.txt```.

## Scores

| Soultion          | Score HR@10   | Set                                       | tune_recommender                | note    |
| ---               | ---           | ---                                       | ---                             | ---     |
|v1 - pandas error  | 0.001645      | user_room_segment, user_n_people_bucket   | LinearRegressionCBUIRecommender |         |
|v2                 | 0.002303      | user_room_segment, user_n_people_bucket   | LinearRegressionCBUIRecommender |         |
|v2                 | <0.026983, 0.029286>      | full                                      | LinearRegressionCBUIRecommender |         |
|v2                 | 0.046726      | full                                      | SVRCBUIRecommender              | slow    |
|v2                 | 0.037183      | full                                      | RandomForestCBUIRecommender     |         |
|v2                 | 0.001645      | full                                      | XGBoostCBUIRecommender          |         |
|v2                 | 0.022047      | full                                      | LinearRegressionCBUIRecommender | update room_segment -> every 100        |
|v2                 | 0.015137      | full                                      | LinearRegressionCBUIRecommender | plus seasons       |
|v2                 | 0.01382       | full                                      | LinearRegressionCBUIRecommender | minus rate_plan     |
|v2                 | 0.030713      | full                                      | LinearRegressionCBUIRecommender | update filter_out_long_stays to 14 from 21     |
|v2                 | 0.026608      | full                                      | LinearRegressionCBUIRecommender | plus filter_out_long_stays    |
|v2                 | <0.051852, 0.052189>      | full                                      | SVRCBUIRecommender | plus filter_out_long_stays + update filter_out_long_stays to 14 from 21   |