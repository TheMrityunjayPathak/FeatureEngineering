## Feature Engineering

- Feature engineering is the process of using domain knowledge to extract or create features from raw data that make machine learning algorithms work better. 
- It is a crucial step in the data preprocessing pipeline, as the quality and relevance of features directly impact the performance of predictive models.

## Theoretical Foundations

**Understanding Features**
  
- Features are the input variables used by machine learning models to make predictions.
- Each feature represents a specific aspect of the data.

| Type of Feature | Detail |
|:---|:---|
| Numerical | Continuous values (e.g. height, weight) or discrete values (e.g. counts). |
| Categorical | Non-numerical values that represent categories (e.g. color, brand).  |
| Ordinal | Categorical variables with a clear ordering (e.g. high school < bachelor < master). |
| Binary | Variables that can take on one of two possible values (e.g. yes/no, true/false). |

**Feature Representation**
  
- The way features are represented can greatly affect a model’s ability to learn.
- Different algorithms require different types of feature representations.

| Models | Detail |
|:---|:---|
| Linear | Perform well with linearly separable data, hence polynomial features or interaction terms may be necessary. |
| Tree-Based | Naturally handle non-linear relationships but can benefit from well-defined feature engineering. |
      
**Curse of Dimensionality**

- As the number of features increases, the volume of the space increases leading to sparsity.
- In high-dimensional space, data points become less similar making it difficult for algorithms to generalize well.
- Effective feature engineering can mitigate this by reducing dimensionality.
 
**Feature Importance**

- Understanding which features contribute most to the model’s predictions can guide feature selection and engineering efforts.
- Techniques like feature importance scores from tree-based models or recursive feature elimination can aid this process.

## Concepts Covered

### Data Standardization
- Data standardization involves scaling your data to have a mean of zero and a standard deviation of one.
- This process is particularly useful when features have different units and scales.

### Example
```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
X_standardized = scaler.fit_transform(X)
```

### Data Normalization
- Normalization scales the features to a range between 0 and 1.
- This technique is beneficial for algorithms that rely on distance measurements, like k-NN.

### Example
```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()
X_normalized = scaler.fit_transform(X)
```

### Encoding Categorical Data
- Categorical data needs to be converted into numerical format for most machine learning algorithms.
- Common techniques include one-hot encoding and label encoding.

### Example
```python
from sklearn.preprocessing import OneHotEncoder

encoder = OneHotEncoder()
X_encoded = encoder.fit_transform(X_categorical).toarray()
```

### Sklearn ColumnTransformer
- The `ColumnTransformer` allows you to apply different preprocessing steps to different columns of your dataset in a concise way.

### Example
```python
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler, OneHotEncoder

preprocessor = ColumnTransformer(
    transformers=[
        ('num', StandardScaler(), numeric_features),
        ('cat', OneHotEncoder(), categorical_features)
    ]
)

X_transformed = preprocessor.fit_transform(X)
```

### Sklearn Pipeline
- The `Pipeline` class enables you to streamline the preprocessing and modeling steps into a single object, ensuring that all steps are applied consistently.

### Example
```python
from sklearn.pipeline import Pipeline

pipeline = Pipeline(steps=[
    ('preprocessor', preprocessor),
    ('model', SomeEstimator())
])

pipeline.fit(X_train, y_train)
```

### Handling Mixed Variables
- When your dataset contains both numerical and categorical variables, it's important to apply appropriate preprocessing to each type.
- Use `ColumnTransformer` as mentioned above for effective handling.

### Missing Categorical Data
- Handling missing data in categorical variables can be done by replacing them with the most frequent category or using advanced techniques like KNN imputation.

### Example
```python
from sklearn.impute import SimpleImputer

imputer = SimpleImputer(strategy='most_frequent')
X_imputed = imputer.fit_transform(X_categorical)
```

### KNNImputer
- The `KNNImputer` uses the k-nearest neighbors algorithm to impute missing values, considering the values of similar data points.

### Example
```python
from sklearn.impute import KNNImputer

imputer = KNNImputer(n_neighbors=5)
X_imputed = imputer.fit_transform(X)
```

### SimpleImputer
- The `SimpleImputer` is a straightforward way to handle missing values using different strategies (mean, median, most frequent, constant).

### Example
```python
from sklearn.impute import SimpleImputer

imputer = SimpleImputer(strategy='mean')
X_imputed = imputer.fit_transform(X_numeric)
```

### Outlier Detection
- Outliers can significantly impact the performance of machine learning models. Several techniques can be employed for outlier detection.

### Using IQR
- The Interquartile Range (IQR) method detects outliers by calculating the range between the first (Q1) and third quartiles (Q3).

### Example
```python
Q1 = np.percentile(X, 25)
Q3 = np.percentile(X, 75)
IQR = Q3 - Q1
outliers = (X < (Q1 - 1.5 * IQR)) | (X > (Q3 + 1.5 * IQR))
```

### Using Z-Score
- Z-score measures how many standard deviations an element is from the mean. A common threshold is 3 to -3.

### Example
```python
X_mean = X.mean()
X_std = X.std()

X_Zscore = (X - X.mean())/X.std()

outliers = (X_Zscore > 3) | (X_Zscore < -3)
```

### Using Winsorization
- Winsorization involves capping extreme values to reduce the impact of outliers.

### Example
```python
upper_limit = np.percentile(X, 95)
lower_limit = np.percentile(X, 5)

outliers = (X < lower_limit) | (X > upper_limit)
```

### Function Transformer
- The `FunctionTransformer` allows you to apply any custom function to your data as part of a pipeline.

### Example
```python
from sklearn.preprocessing import FunctionTransformer

def custom_function(X):
    return X ** 2

transformer = FunctionTransformer(func=custom_function)
X_transformed = transformer.fit_transform(X)
```

### Power Transformer
- The `PowerTransformer` can help stabilize variance and make the data more Gaussian-like.
- This is useful for improving the performance of models that assume normally distributed data.

### Example
```python
from sklearn.preprocessing import PowerTransformer

transformer = PowerTransformer()
X_transformed = transformer.fit_transform(X)
```

### Imbalance Data
- Imbalanced data refers to a situation where the distribution of classes within a dataset is not uniform.
- This is particularly common in classification problems where one class significantly outnumbers the other class.

### Example
```python
# Under Sampling
from imblearn.under_sampling import RandomUnderSampler
rus = RandomUnderSampler()
X_rus, y_rus = rus.fit_resample(X_train, y_train)

# Over Sampling
from imblearn.over_sampling import RandomOverSampler
ros = RandomOverSampler()
X_ros, y_ros = ros.fit_resample(X_train, y_train)

# Synthetic Minority Over-sampling Technique
from imblearn.over_sampling import SMOTE
smote = SMOTE()
X_smote, y_smote = smote.fit_resample(X_train, y_train)
```

### Principal Component Analysis
- Principal component analysis (PCA) reduces the number of dimensions in large datasets to principal components that retain most of the original information.
- It does this by transforming potentially correlated variables into a smaller set of variables called principal components.

### Example
```python
# Importing PCA
from sklearn.decomposition import PCA

# Creating PCA Object for 2 Features
pca = PCA(n_components=2)

# Fit and Transform on Training Data
X_train_pca = pca.fit_transform(X_train_scaled)

# Transforming Testing Data
X_test_pca = pca.transform(X_test_scaled)
```

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

<div align='right'>
  
**[`^        Scroll to Top       ^`](#feature-engineering)**

</div>
