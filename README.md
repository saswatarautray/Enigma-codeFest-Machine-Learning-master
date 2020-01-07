# Enigma-codeFest-Machine-Learning

The approach I implemented for the Analytics Vidhya Enigma-codeFest-Machine-Learning Competition, I got a public Leaderboard loss of 768.49 and ranked 11th.

My approach to the solution was straight forward. Firstly, I performed data visualization to see the distribution of data. I used seaborn for plotting and finding correlation to identify important features. I plotted a histogram of data and discovered that features like Reputation and Views are distributed with very high values and ID, UserName features are not required which can be removed.

I spent the majority of my time on data-preprocessing. I removed unwanted features, filtering, scaling and performed feature engineering which was a vital element for accuracy. I used Binarizer as a new feature in my training data, which tells whether Answers features have, above a threshold, some value or not.

I tried different algorithms like SVR, SGDRegressor and decision tree but neither of them worked as I expected at first as the distribution of data is polynomial. Hence, I took PolynomialRegressor with Linear regression LassoLars. I found it to be the best fit for this type of data.

Cross-validation was important. I split my data with test size 0.22, trained it to get an r2 score 0.91 on the validation set. To get a less loss I tested different approaches like Xgboost, Progressive Learning, ANN but neither of them worked as they tended to overfit. Therefore, I decided to fine-tune hyperparameter to get a good score.

An important outliner I discovered was the Views feature. So, I removed values if it was more than 3000000 from the training set as I discovered that only four values similar existed in the testing set, which contributed to the majority of the loss. After removing those scores and varying my Binarizer threshold, my rank improved and I ranked 6th in public scoreboard but in the overall ranking I ranked 11th and I believe the reason is that I still should have tried simpler approaches such as linear regression to get a high rank in the private scoreboard.
