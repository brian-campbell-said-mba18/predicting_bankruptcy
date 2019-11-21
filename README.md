# Description
Brian Campbell's Udacity Capstone Project. This builds upoon Mattson & Steinert's research on predicting bankruptcies in Polish manufacturing companies.

[Bachelor's thesis](https://gupea.ub.gu.se/handle/2077/54283) by [Björn Mattsson](https://www.linkedin.com/in/björn-mattsson-02357b70) and 
[Olof Steinert](https://www.linkedin.com/in/olof-steinert/) in Economics at 
[University of Gothenburg](http://handels.gu.se/).

## Mattson & Steinert's Abstract
Estimating the risk of corporate bankruptcies is of large importance to creditors and investors. For this reason bankruptcy prediction constitutes an important area of research. In recent years artificial intelligence and machine learning methods have achieved promising results in corporate bankruptcy prediction settings. Therefore, in this study, three machine learning algorithms, namely random forest, gradient boosting and an artificial neural network were used to predict corporate bankruptcies. Polish companies between 2000 and 2013 were studied and the predictions were based on 64 different financial ratios.

The obtained results are in line with previously published findings. It is shown that a very good predictive performance can be achieved with the machine learning models. The reason for the impressive predictive performance is analysed and it is found that the missing values in the data set play an important role. It is observed that prediction models with surprisingly good performance could be achieved from only information about the missing values of the data and with the financial information excluded.

Keywords: Economics, Corporate bankruptcy prediction, Machine learning, Neural networks, Missing values

## The Real Abstract:
Mattson et al made critical errors in preprocessing the data. Mattson et al broke down the dataset into five distinct datasets, a dataset for each of the five years (Reference 7; Reference 17). They then created three different versions of the data for each year: the first had no null values in the data, while the second and third had null values (Reference 7). Furthermore, version one had no feature variables regarding null values, version two had dummy variables created for each x feature, signaling whether a given value in the x feature was null, and version three had a null counter variable that counted the number of null values in a given row of data (Reference 7). They then split the data for each year and each version of the data. The error that Mattson et al overlooked was that the second and fourth year datasets contained rows that contained at least one null value (see Appendices B and C). They probably imputed values for the nulls in the second and fourth years, which one cannot do in a dataset that has at least one null value in each row. If every row has at least one null value, then it is impossible to create a testing set without imputing values into it, which would introduce data leakage, model information outside the scope of the training set, into the testing set (Reference 18; Reference 19). Data leakages lead to overly optimistic models, and avoiding obvious sources of data leakages, such as imputing values into the testing data, is common practice in building machine learning models (Reference 18; Reference 19). The violation of this practice necessitates that a different methodology from Mattson et al’s be used.

The new problem this analysis addresses is given that Mattson et al’s models are probably overly optimistic due to data leakage, how well should an MLP model, not corrupted by imputed values in the testing data, perform in predicting bankruptcy? Also, along with a new methodology that protects the model from data leakage, this analysis will also need a new benchmark for performance. Logistic regression models are used as the benchmark for the MLP models. The metric used to measure the efficacy of these models are AUC scores.


# How to run

* Ignore any file that looks like this: OLD_filename_OLD. Those are Mattson & Steinart's scripts that I don't use for my analysis.
* To run the data cleaning and preprocessing part of the analyisis, run bankruptcy-data.ipynb.
* To run the benchmark logistic regression and MLP models, run bankruptcy-model.ipynb.

## Software Info

* Python 3.6.7
* TensorFlow 3.6.7
