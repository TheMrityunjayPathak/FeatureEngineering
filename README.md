## Feature Engineering

- Feature engineering is a machine learning technique that leverages data to create new variables that aren’t in the training set.

- It can produce new features for both supervised and unsupervised learning, with the goal of simplifying and speeding up data transformations while also enhancing model accuracy. 

- Feature engineering is required when working with machine learning models. 

- Regardless of the data or architecture, a terrible feature will have a direct impact on your model.

## Importance of Feature Engineering

- Feature Engineering is a very important step in machine learning.

- Feature engineering refers to the process of designing artificial features into an algorithm.

- These artificial features are then used by that algorithm in order to improve its performance.

## Notebook List

Here is a list of Jupyter Notebooks included in this repository :

[Dummy Variable](https://www.kaggle.com/code/themrityunjaypathak/dummy-variable)

- Dummy variables are qualitative variables or discrete variables that represent categorical data and can take the values as 0 or 1 to indicate the absence or presence of a specified attribute respectively.

[Inter Quartile Range](https://www.kaggle.com/code/themrityunjaypathak/removing-outlier-from-data-using-iqr)

- In Descriptive Statistics, the Interquartile Range tells you the spread of the middle half of your distribution.

- Quartiles segment any distribution that’s ordered from low to high into four equal parts. 

- The interquartile range (IQR) contains the second and third quartiles, or the middle half of your data set.

**The Interquartile Range is found by subtracting the Q1 value from the Q3 value :**

- IQR = Q3 - Q1
- Q3 = 3rd quartile or 75th percentile
- Q1 = 1st quartile or 25th percentile

- Q1 is the value below which 25 percent of the distribution lies, while Q3 is the value below which 75 percent of the distribution lies.

[Z-Score](https://www.kaggle.com/code/themrityunjaypathak/removing-outlier-from-data-using-zscore)

- Z-score is a statistical measurement that describes a value's relationship to the mean of a group of values.

- Z-score is measured in terms of standard deviations from the mean.

- Z-scores may be positive or negative, with a positive value indicating the score is above the mean and a negative score indicating it is below the mean.

- The statistical formula for a value's z-score is calculated using the following formula:

**Z-Score = ( x - μ ) / σ**

where :

- z = Z-score
- x = the value being evaluated
- μ = the mean
- σ = the standard deviation

[Modified Z-Score](https://www.kaggle.com/code/themrityunjaypathak/removing-outlier-from-data-using-modified-zscore)

- A Modified Z-Score is more robust because it uses the median to calculate z-scores as opposed to the mean, which is known to be influenced by outliers.

**Modified Z-Score = 0.6745(xi – x̃) / MAD**

where :

- xi = A single data value
- x̃ = The median of the dataset
- MAD = The median absolute deviation of the dataset

- Value's with Modified Z-Scores less than -3.5 or greater than 3.5 be labeled as potential outliers.

[Data Standardization](https://www.kaggle.com/code/themrityunjaypathak/data-standardization)

- Standardization is a scaling method where the values are centered around the mean with a unit standard deviation.

- This means that the mean of the attribute becomes zero, and the resultant distribution has standard deviation equal to 1.

[Handling Imbalance Dataset](https://www.kaggle.com/code/themrityunjaypathak/handling-imbalance-dataset)

- Imbalanced data refers to those types of datasets where the target class has an uneven distribution of observations.

- In an Imbalance Data one class label has a very high number of observations and the other has a very low number of observations.

## Getting Started

- You can clone this repository using the following command:
  ```
  git clone https://github.com/TheMrityunjayPathak/FeatureEngineering.git
  ```

- Install the Jupyter Notebook :
   ```bash
   pip install notebook
   ```

- Launch the Jupyter Notebook :
   ```bash
   jupyter notebook
   ```

- Open the desired notebook from the repository in your Jupyter environment and start learning!

## Contributing

- Contributions are Welcome! 

- If you'd like to contribute to this repository, feel free to submit a pull request.

## License

- This repository is licensed under the [MIT License](LICENSE). 

- You are free to use, modify and distribute the code in this repository.

| [Scroll to Top ⬆️](#feature-engineering) |
|:---:|
