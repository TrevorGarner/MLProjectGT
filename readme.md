# ML Project for CS 4641 Machine Learning @ Georgia Tech (Group #18)

## Project Proposal - Predicting Top Chart Songs Using Spotify Data:

![Header](/images/header.png)

__Introduction/Background/Problem Definition:__
Our goal is to produce a predictive model using supervised learning. Our product should be able to predict if a certain song will chart in the top 50 of Billboard’s Hot 100 based on certain features. Through this project, we’ll analyze how the world’s music taste has shifted over the last decade. If time permits, we may see which features affect the popularity of a song/track the most.

__Data Set:__ [Billboard Weekly Hot 100 Charts](https://data.world/kcmillersean/billboard-hot-100-1958-2017)
We are dealing with two data sets: one from Billboard Hot 100 and one taken from Spotify’s API [8]. 

![Spotify Features](/images/spotifyfeatures.png)

__Methods:__
We want to train a binary classification model that will give us a discrete answer to our question of if the given song will chart in the top 50. The general procedure will go as follows: train the appropriate model on our training dataset, which is the past top 100 songs. Then, we can use our trained model to predict the current top 50 songs and evaluate the error between the model’s prediction and actual results.

Logistic regression is an appropriate technique for classifying a binary dependent variable. It uses the sigmoid function to predict the probability (p(x)) of an event and returns 0 if p(x) < 0.5 and 1 if p(x) > 0.5 [6]. So, we can train a logistic regression model using features from the dataset, and use it to make predictions on new data.

Another classification algorithm that we could use is with decision trees. We can have either classification or regression trees [7], so in this case, we would want to use a binary classification tree. These trees have discrete decision variables, so we will get a result that will predict either “yes” or “no”.

__Potential Results:__
![Graph](/images/graphProposal.jpeg)

Above is a visualization of our logistic regression model, where the blue curve is the sigmoid function that determines the classification of each datapoint. The x’s and circles represent songs, and we can see in the key in the top left corner how the points corresponding to a higher probability are classified as 1s, and the points matching a lower probability are classified as 0s.

![Graph2](https://miro.medium.com/max/1200/1*_xpHkZNnvVJC0XKYYO6D8g.png)

Our decision tree nodes will look something like this, where each arrow points to a new node for a new feature until we reach a decision. Here we can visualize how the tree will be able make a discrete binary decision.
For both of these methods, we can calculate the accuracy by dividing the number of correct predictions by the number of total predictions made. We want to use whatever model consistently produces the highest accuracy (the lowest error rate) [4].

__Discussion:__
Several models have been proposed to predict a song’s success [1]. From current results, Linear Regression and Neural Net models have the highest accuracy of 73% and 77% respectively [2]. However, changing the time parameters to focus on recent music from 2015 to 2018 yielded better results for the NN with an accuracy of around 86% but worse results for LR with a rating of around 72% [2]. This shows that newer songs are becoming harder to predict with previous models. It’s possible that between 2015 to 2018 there was a change occurring in the overall taste of music or that the general population was becoming more aware of other genres of music. Thus, it will be important to try different variations of models to ensure a high accuracy rating is achieved.

__References:__
[1] https://towardsdatascience.com/song-popularity-predictor-1ef69735e380
[2] http://cs229.stanford.edu/proj2018/report/16.pdf
[3] https://github.com/siddgood/billboard-hit-prediction
[4] https://data.library.virginia.edu/visualizing-the-effects-of-logistic-regression/
[5] https://developer.spotify.com/documentation/web-api/reference/tracks/get-audio-features/
