# EECS731-D-St-reams-of-Anomalies

This is the project of EECS 731 Data science.

(1) Content

|-READ.ME |-anomaly detection.ipynb |-data | |-cpu_utilization_asg_misconfiguration.csv

(2) Ideas 

By plot the first 100 data points we can eye-identify some outliers, so I applied 4 models to identify the outliers, 2 supervied: Random Forest(RFC) and one-class SVM(SVM), and 2 unsupervised: Isolated Forest(IF) and Local Outlier Factor(LCF). 
Since the supervised model needs labeled training data, I define the data points with value outside close interval [m-3*delta, m+3*delta] as outliers, labeled by -1, whereas the inliers are labeled by 1. Here m is the arithmetic mean of all values and delta is the standard deviation of the value.
For performance measuring, I am going to use F1 score instead of accuracy since the 'anomaly' is supposed to be rare, so the data itself will be skewed/biased. 
The result shows that RF has perfect performance on this task. The detailed ranking is as following:
F1 score on training set: RF > SVM > IF > LCF
F1 score on testing set: RF > SVM > IF > LCF
However, SVM is the only model here which fails to identify all outliers as defined before.
