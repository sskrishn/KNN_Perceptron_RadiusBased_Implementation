# KNN_Perceptron_RadiusBased_Implementation
*Program to implement KNN classifier , Perceptron and Radius based classifier from scratch and decide best classifier on given data*

To come up with a classifier that can predict the stress class of new couples based on Income of Husband and Income of wife for the given data set which contains 399 records with their income as Features and self-assessed level of stress as target variable. We are consider KNN and Single Perceptron classifiers. Also to same dataset we need to implement a classification algorithm similar to knn but instead of k we will use radius which will be used to make a decision based on majority of those points.

# Strategy (for KNN):
*File : knn_perceptron_implementation.ipynb*

•	As data contain only two features (independent variables) there is no need of dimension deduction. 

•	Data is almost balanced and also we observed that it is not linearly separable from the plot and so KNN can be used as a classifier to get good results.

•	Here given features are values of income and both are on same scale. As KNN involves finding distances between features it is required all the features should be on same scale. Though given features are on same scale, they are having high values and so a scaling normalization to range of 0 and 1 will help in good classification using KNN. So after using MinMax Normalization for given dataset, the plot will be as shown in fig 1.2

•	Also Data is divided into test and train data such that test data will be 20% and train data will be used as referenced data for KNN.

•	Here we will try for different values of k ranging from 1 to 50 and also used 5 different trails to get error rates for different k values.

**•	Augmentations :**

a) I have used 3 different distances Manhattan, Euclidean and Chebyshev for calculating distances in KNN algorithm.

b) Also used 2 different versions which includes weighted version of knn. For one version, we will calculate distances of test point with other train points and predict it using max count of labels of k nearest neighbors. For other version, Inverse of square of distances is used as metric to decide the class of test point. In my method, normalKNN and weightedKNN are the options to have different versions of KNN.

# Strategy (For perceptron):
*File : knn_perceptron_implementation.ipynb*


•	For perceptron also we need to scale/normalize the data as weights updating involves the product of input features and so it should be small else take long steps in gradient descent.

•	I have started by initializing weights and bias with 0’s and training has been done for 50 epochs. Here weights are updating for every input in every epoch.

•	Also we have considered Learning rate = 0.01 which is constant throughout the process.

# Strategy (For Radius based):
*File : knn_radiusBased_implementation.ipynb*

•	Followed same process of KNN. (To calculate range of R values, I have calculated distance matrix which will contain the distances of all features. This is because when we select the different radii with greater than maximum of distances of all points in given data, all test data given to classifier will result to same set of predictions always. So I have used concept similar to binning but not binning, to get the range of 10 r values for which I have taken max and min distances of all points and got 10 equally spaced r values. R ranging from 0.11 to 1.07 in equally spaced values.)

**Observations:**

In conclusion we can state that as the given dataset is not linearly separable and also from the graphs that the KNN with 9 nearest neighbors with options Euclidean and normalKNN using 5 different trails validation gives the best classifier to predict the stress class with hit rate of 0.925. My opinion on pros and cons of the classifiers are that hypothesis for KNN is complex and involves more cost whereas Perceptron always gives straight line equation and comes into excellent use when data is linearly separable. But KNN gives good results as it provides curve fit instead of line for non-linear separable data. KNN is easy to implement. It does not involves training whereas perceptron involves training. So while testing or predicting, KNN takes more time when compared to perceptron. My recommendation is to get good accuracy at cost of time prefer KNN. Also KNN giving good results compared to Radius based classifier.



