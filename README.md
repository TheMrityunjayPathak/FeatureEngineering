👉 **What is Feature Engineering?**

Feature engineering is a machine learning technique that leverages data to create new variables that aren’t in the training set.

It can produce new features for both supervised and unsupervised learning, with the goal of simplifying and speeding up data transformations while also enhancing model accuracy. 

Feature engineering is required when working with machine learning models. Regardless of the data or architecture, a terrible feature will have a direct impact on your model.

👉 **Importance of Feature Engineering**

Feature Engineering is a very important step in machine learning.

Feature engineering refers to the process of designing artificial features into an algorithm.

These artificial features are then used by that algorithm in order to improve its performance, or in other words reap better results.

Data scientists spend most of their time with data, and it becomes important to make models accurate.

👉 **Topics Covered in Repository**

- [Dummy Variable](https://www.kaggle.com/code/themrityunjaypathak/dummy-variable)

Dummy variables are qualitative variables or discrete variables that represent categorical data and can take the values as 0 or 1 to indicate the absence or presence of a specified attribute respectively.

- [Inter Quartile Range](https://www.kaggle.com/code/themrityunjaypathak/removing-outlier-from-data-using-iqr)

IQR is used to measure variability by dividing a data set into quartiles.

The data is sorted in ascending order and split into 4 equal parts. Q1, Q2, Q3 called first, second and third quartiles are the values which separate the 4 equal parts.

- Q1 represents the 25th percentile of the data.
- Q2 represents the 50th percentile of the data.
- Q3 represents the 75th percentile of the data.

IQR is the range between the first and the third quartiles namely Q1 and Q3 : IQR = Q3 – Q1. 

The data points which fall below Q1 – 1.5 IQR or above Q3 + 1.5 IQR are outliers.

- [Z-Score](https://www.kaggle.com/code/themrityunjaypathak/removing-outlier-from-data-using-zscore)

Z-score is a statistical measurement that describes a value's relationship to the mean of a group of values.

Z-score is measured in terms of standard deviations from the mean. 

- If a Z-score is 0, it indicates that the data point's score is identical to the mean score.
- A Z-score of 1.0 would indicate a value that is one standard deviation from the mean.
- Z-scores may be positive or negative, with a positive value indicating the score is above the mean and a negative score indicating it is below the mean.

- [Modified Z-Score](https://www.kaggle.com/code/themrityunjaypathak/removing-outlier-from-data-using-modified-zscore)

A modified z-score is more robust because it uses the median to calculate z-scores as opposed to the mean, which is known to be influenced by outliers. 

Values with modified z-scores less than -3.5 or greater than 3.5 be labeled as potential outliers.

- [Data Standardization](https://www.kaggle.com/code/themrityunjaypathak/data-standardization)

Data standardization is the process of converting data to a common format to enable users to process and analyze it.

Features will be rescaled to ensure the mean and the standard deviation to be 0 and 1, respectively.
