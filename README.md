# Description
Brian Campbell's Udacity Capstone Project. This builds upoon Mattson & Steinert's research on predicting bankruptcies in Polish companies.

[Bachelor's thesis](https://gupea.ub.gu.se/handle/2077/54283) by [Björn Mattsson](https://www.linkedin.com/in/björn-mattsson-02357b70) and 
[Olof Steinert](https://www.linkedin.com/in/olof-steinert/) in Economics at 
[University of Gothenburg](http://handels.gu.se/).

## Mattson & Steinert's Abstract
Estimating the risk of corporate bankruptcies is of large importance to creditors and investors. For this reason bankruptcy prediction constitutes an important area of research. In recent years artificial intelligence and machine learning methods have achieved promising results in corporate bankruptcy prediction settings. Therefore, in this study, three machine learning algorithms, namely random forest, gradient boosting and an artificial neural network were used to predict corporate bankruptcies. Polish companies between 2000 and 2013 were studied and the predictions were based on 64 different financial ratios.

The obtained results are in line with previously published findings. It is shown that a very good predictive performance can be achieved with the machine learning models. The reason for the impressive predictive performance is analysed and it is found that the missing values in the data set play an important role. It is observed that prediction models with surprisingly good performance could be achieved from only information about the missing values of the data and with the financial information excluded.

Keywords: Economics, Corporate bankruptcy prediction, Machine learning, Neural networks, Missing values

## The Real Abstract:
Mattson & Steinert's Multilayer Perceptron (MLP) algorithm performed the worst. I believe with some work on the hyperparameters, the accuracy could improve. I will use area under the curve (AUC) of the Receiver Operating Characteristic (ROC) to measure the accuracy of my algorithms. Mattson & Steinert used AUC.

## Bugs:
The results of my first and only algorithm are beyond stupid (the algorithm can be found in MLP.py). I get 0.0000 validation accuracies for all the epochs of my algorithm. I believe the culprit could be one of several things. First, I intentionally run my algorithm with NaN values and that could be messing it up (perhaps I simply need to change all my NaN values to zeros). Second, I'm not sure if I pre-processed my target variable correctly. It's a binary variable with 1 = bankrupt, and 0 = not bankrupt. While I performed standard scaling on my X variables, I figured I did not need to process the 1s and 0s in my Y variable (was this a mistake). Please help.


# How to run

* Ignore any file that looks like this: OLD_filename_OLD. Those are Mattson & Steinart's scripts that I don't use for my analysis.
* Simply run bankruptcy-neural-network-analysis.ipynb


## Version info

* Python 3.6
