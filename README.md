# Dataset

## First inning ball to ball coverage of:

* 1188 ODI matches -> data/odi.csv
* 1474 T-20 matches -> data/t20.csv
* 617 IPL matches -> data/ipl.csv

## Each dataset consists of the following columns:

* mid -> Each match is given a unique number
* date -> When the match happened
* venue -> Stadium where match is being played
* bat_team -> Batting team name
* bowl_team -> Bowling team name
* batsman -> Batsman name who faced that ball
* bowler -> Bowler who bowled that ball
* runs -> Total runs scored by team at that instance
* wickets -> Total wickets fallen at that instance
* overs -> Total overs bowled at that instance
* runs_last_5 -> Total runs scored in last 5 overs
* wickets_last_5 -> Total wickets that fell in last 5 overs
* striker -> max(runs scored by striker, runs scored by non-striker)
* non-striker -> min(runs scored by striker, runs scored by non-striker)
* total -> Total runs scored by batting team after first innings

# Prediction Algorithm and Accuracy

## Algorithms Used

1. Linear Regression -> linear_regression.py
2. Random Forest Regression -> random_forest_regression.py

## Features and Label Used

* Features: [runs,wickets,overs,striker,non-striker]
* Label: [total]

## Accuracy in terms of [R Square Value,Custom Accuracy]

1. Linear Regression
   * ODI matches  -> [52,43]
   * T-20 matches -> [52,44]
   * IPL matches  -> [50,44]
2. Random Forest Regression
   * ODI matches  -> [79,77]
   * T-20 matches -> [64,59]
   * IPL matches  -> [67,65]

**Note:**
Custom Accuracy is defined on the basis of difference between the predicted score and actual score. If this difference falls below a particular thresold, we count it as a correct prediction.

* T-20 thresold: 10
* ODI thresold: 20

# Testing the code

```
git clone https://github.com/codophobia/CricketScorePredictor.git
cd CricketScorePredictor
virtualenv -p python3 venv
source venv/bin/activate
pip3 install -r requirements.txt
python3 linear_regression.py or random_forest_regressor.py
```

**Note:**
I have hardcoded the ODI dataset in the code. You can change it to other datasets and test it. You can also play with other features which are included in the dataset. You can also play along with the Custom accuracy thresolds.
