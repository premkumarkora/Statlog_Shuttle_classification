# Statlog_Shuttle_classification
Stat Log Shuttle Classification 


The shuttle dataset contains 9 attributes all of which are numerical.
The first one being time.  The last column is the class which has been 
coded as follows :
        1       Rad Flow
        2       Fpv Close
        3       Fpv Open
        4       High
        5       Bypass
        6       Bpv Close
        7       Bpv Open
        
Approximately 80% of the data belongs to class 1. Therefore the default 
accuracy is about 80%. The aim here is to obtain an accuracy of 
99 - 99.9%.

In this example, I have used Logistic regression.

As data is clean, We did the following to achive 99.99 Accuracy

1. Find the ouliers
2. Remove outliers.
3. After removing outliers we are seeking a specific class of data is removed, So added back these data 
4. looked into 
target_count = df.target.value_counts()
print(target_count)
target_count.plot(kind='bar', title='Count (target)')

1    34108
4     6748
5     2458
3      132
2       37
7       11
6        6

The Target values are distrubuted, So I looked at how to remove the imbalance the data

from imblearn.combine import SMOTEENN
smt = SMOTEENN(sampling_strategy='all')
X_smt, y_smt = smt.fit_resample(X, y)
X_smt.shape

(238549, 9)

Original data was (43500, 10)

We have increased the data set for all the target varibles.

I used Logistic Regression After executing the below code 
print('Accuracy',logistic_regression.score(X_test,y_test))
We get a Accuracy 0.9999580800670719

