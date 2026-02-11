OneHotEncoder class converts categorical values into one-hot vectors:  one attribute will be equal to 0, and the others will be 1. Question 1 options: TrueFalse

12:19 PM

**False**

One-hot encoding works the opposite way: **one attribute will be equal to 1, and the others will be 0**.

For example, if you have a categorical variable "color" with values ["red", "green", "blue"], one-hot encoding would convert:

- "red" → [1, 0, 0]
- "green" → [0, 1, 0]
- "blue" → [0, 0, 1]

Each category gets its own binary column, and exactly one of those columns has a value of 1 (indicating the presence of that category), while all others are 0.

To fix missing values for an attribute, three options are recommended in Chapter 2. Which one is called imputation? Question 2 options: a)  Get rid of the corresponding districts b)  Set the missing values to some value (zero, the mean, the median, etc.). c)  Get rid of the corresponding district

12:19 PM

**b) Set the missing values to some value (zero, the mean, the median, etc.).**

Imputation is the process of filling in missing values with estimated or calculated values rather than removing the data. Common imputation strategies include:

- Using the mean or median of the attribute
- Using the most frequent value (mode)
- Using a constant value like zero
- Using more sophisticated methods like k-nearest neighbors

The other options (a and c, which are the same) describe deletion strategies, not imputation.

![1770661314315_image.png](/api/22535840-d82a-47f7-9618-1b4d4ac5fe28/files/73d0500c-cdf3-4f03-890f-1751375168f6/preview)

12:21 PM

**d) To create an income category attribute with five categories (labeled from 1 to 5); category 1 ranges from 0 to 1.5 (i.e., less than $15,000), category 2 from 1.5 to 3, and so on.**

The `pd.cut()` function is used to bin continuous data into discrete intervals (categories). In this code:

- `bins=[0., 1.5, 3.0, 4.5, 6., np.inf]` defines the edges of the bins/categories
- `labels=[1, 2, 3, 4, 5]` assigns labels 1-5 to each category
- The result is a new categorical attribute `income_cat` that classifies each district's median income into one of five categories

This is a common technique for stratified sampling, where you want to ensure your training and test sets have representative proportions of different income levels.

The following code sequentially applies all the transformers defined in num_pipeline to the data housing_num. num_pipeline = make_pipeline(SimpleImputer(strategy="median"), StandardScaler()) num_pipeline.fit_transform(housing_num) Question 4 options: a) Trueb) False

12:22 PM

**a) True**

The code creates a pipeline using `make_pipeline()` that sequentially applies:

1. `SimpleImputer(strategy="median")` - fills missing values with the median
2. `StandardScaler()` - standardizes features by removing the mean and scaling to unit variance

When `num_pipeline.fit_transform(housing_num)` is called, it applies both transformers in sequence to the `housing_num` data. The output of the first transformer (SimpleImputer) becomes the input to the second transformer (StandardScaler).

![1770661468761_image.png](/api/22535840-d82a-47f7-9618-1b4d4ac5fe28/files/191a74d3-7d1a-4668-94f5-ad10aceca62b/preview)

What does the following code generate?

Question 6 options: It generates 10 training sets and 10 test sets from housing. It generates 10 different income categories from the data set housing. It generates 10 different stratified splits of the same dataset housing.

12:24 PM

**It generates 10 different stratified splits of the same dataset housing.**

The code uses `StratifiedShuffleSplit` with `n_splits=10`, which creates 10 different train/test splits of the housing dataset. Each split:

- Maintains the same proportions of the `income_cat` categories in both training and test sets (stratified sampling)
- Uses a test size of 20% (`test_size=0.2`)
- Is randomized but reproducible (`random_state=42`)

The loop iterates through all 10 splits, and for each split, it creates a training set and test set pair, then appends them as a tuple to the `strat_splits` list. So you end up with 10 different ways to divide the same housing dataset, each preserving the income category distribution.

If housing is an object of DataFrame, the method housing.info() is used for providing information about the constructor of housing. Question 7 options: a) Trueb) False

12:25 PM

**b) False**

The `housing.info()` method does **not** provide information about the constructor. Instead, it provides a concise summary of the DataFrame including:

- The number of rows and columns
- Column names
- Data types of each column
- Number of non-null values in each column
- Memory usage

It's used for getting a quick overview of the dataset's structure and identifying missing values, not for information about how the DataFrame was constructed.

Given the following code >>> mydict = [{'a': 1, 'b': 2, 'c': 3, 'd': 4}, ...           {'a': 100, 'b': 200, 'c': 300, 'd': 400}, ...           {'a': 1000, 'b': 2000, 'c': 3000, 'd': 4000}] >>> df = pd.DataFrame(mydict) >>> df what is the correct output? Question 8 options: a)  abcd12341002003004001000200030004000 b)  012a11001000b22002000c33003000d4400400 c)  a11001000b22002000c33003000d4400400 d)  abcd01234110020030040021000200030004000

Show more

12:25 PM

**c)**

```
      a     b     c     d
0     1     2     3     4
1   100   200   300   400
2  1000  2000  3000  4000
```

When you create a DataFrame from a list of dictionaries, each dictionary becomes a row, and the dictionary keys become the column names. The DataFrame automatically assigns integer indices (0, 1, 2) to the rows.

So:

- Column headers: a, b, c, d
- Row 0: 1, 2, 3, 4
- Row 1: 100, 200, 300, 400
- Row 2: 1000, 2000, 3000, 4000

Option c shows this structure (though without the row index column displayed, which is the standard representation).

The following four steps are for fixing missing values using SimpleImputer. Select a correct implementation for each step from given options. Question 9 options: 1234 X = imputer.transform(housing_num) 1234 housing_num = housing.select_dtypes(include=[np.number]) 1234 from sklearn.impute import SimpleImputer imputer = SimpleImputer(strategy="median") 1234 imputer.fit(housing_num) 1. Create a SimpleImputer instance, specifying that you want to replace each attribute's missing values with the median of that attribute.

2. Create a copy of the data with only the numerical attributes (this will exclude the text attribute ocean_proximity).

3. Apply the imputer instance to the training data. 4. Use the "trained" imputer to transform the training set by replacing missing values with the learned medians.

Show more

12:27 PM

Here's the correct order:

**1. Create a SimpleImputer instance, specifying that you want to replace each attribute's missing values with the median of that attribute.**

- **3**: `from sklearn.impute import SimpleImputer imputer = SimpleImputer(strategy="median")`

**2. Create a copy of the data with only the numerical attributes (this will exclude the text attribute ocean_proximity).**

- **2**: `housing_num = housing.select_dtypes(include=[np.number])`

**3. Apply the imputer instance to the training data.**

- **4**: `imputer.fit(housing_num)`

**4. Use the "trained" imputer to transform the training set by replacing missing values with the learned medians.**

- **1**: `X = imputer.transform(housing_num)`

The correct workflow is:

1. Import and create the imputer with the desired strategy
2. Select only numerical columns (since median only works on numerical data)
3. Fit the imputer to learn the median values from the data
4. Transform the data using the learned medians to replace missing values

What is the purpose of the following code? from sklearn.preprocessing import OrdinalEncoder ordinal_encoder = OrdinalEncoder() housing_cat = housing[["ocean_proximity"]] housing_cat_encoded = ordinal_encoder.fit_transform(housing_cat) Question 10 options: To convert categories from text to numbers. To train the model using housing attribute ocean_proximity To covert housing attribute ocean_proximity to true or false value

12:28 PM

**To convert categories from text to numbers.**

The `OrdinalEncoder` converts categorical text values (like "NEAR BAY", "INLAND", "<1H OCEAN", etc.) into numerical values (like 0, 1, 2, 3, etc.). Each unique category is assigned an integer.

For example, the `ocean_proximity` categories might be encoded as:

- "NEAR BAY" → 0
- "INLAND" → 1
- "<1H OCEAN" → 2
- "NEAR OCEAN" → 3
- "ISLAND" → 4

This is necessary because most machine learning algorithms require numerical input rather than text. The ordinal encoder assigns arbitrary integer values to each category, making them usable in mathematical computations.

Scikit-Learn provides the Pipeline class to help with the correct order to execute data transformation steps. Question 13 options: a) Trueb) False

12:29 PM

**a) True**

The `Pipeline` class in Scikit-Learn is specifically designed to ensure that data transformation steps are executed in the correct sequential order. It helps you:

- Chain multiple transformers and estimators together
- Ensure transformations are applied in the proper sequence
- Prevent data leakage by fitting transformers only on training data
- Simplify code by bundling preprocessing and modeling steps
- Make it easier to apply the same sequence of transformations to new data

For example, a pipeline ensures that imputation happens before scaling, and scaling happens before model training, maintaining the correct order throughout the entire workflow.

Given the following code, from sklearn.preprocessing import OneHotEncoder cat_encoder = OneHotEncoder() housing_cat_1hot = cat_encoder.fit_transform(housing_cat) the output housing_cat_1hot is a SciPYy matrix. What does it look like?

Question 15 options: only single 1 and all 0s per row. only single 1 and all 0s per column. only single 0 and all 1s per row. only single 0 and all 1s per column

12:31 PM

**only single 1 and all 0s per row.**

In one-hot encoding, each row represents one data sample, and each column represents one possible category. For each row:

- Exactly **one** column has a value of **1** (indicating which category that sample belongs to)
- All other columns have values of **0**

For example, if `ocean_proximity` has 5 categories, the encoded matrix might look like:

```
[[1, 0, 0, 0, 0],   # Sample 1: category 0
 [0, 1, 0, 0, 0],   # Sample 2: category 1
 [0, 0, 0, 1, 0],   # Sample 3: category 3
 [1, 0, 0, 0, 0]]   # Sample 4: category 0
```

Each row has exactly one 1 and the rest are 0s.

![1770661978249_image.png](/api/22535840-d82a-47f7-9618-1b4d4ac5fe28/files/8a9d204b-e278-4c1e-9c59-548508dcbaf3/preview)

12:32 PM

**b) It shows what categories exist and how many districts belong to each category.**

The `value_counts()` method returns the frequency of each unique value in the `ocean_proximity` column. The output shows:

- **<1H OCEAN**: 9136 districts
- **INLAND**: 6551 districts
- **NEAR OCEAN**: 2658 districts
- **NEAR BAY**: 2290 districts
- **ISLAND**: 5 districts

This gives you a count of how many data samples (districts) fall into each categorical value, which is useful for understanding the distribution of categories in your dataset.

Handling Text and Categorical Attributes • Only one text attributes : the ocean_proximity attribute. Its value for the first few instances can be viewed • There are a limited number of possible values, each of which represents a category. So this attribute is a categorical attribute. • Five categories (see slide #22) here is context

12:33 PM

Thank you for providing that context! This confirms the background for the previous question about `ocean_proximity`.

To summarize the key points about handling this text/categorical attribute:

1. **Text attribute**: `ocean_proximity` is the only text attribute in the housing dataset
2. **Categorical nature**: Despite being text, it has a limited number of possible values, making it categorical
3. **Five categories**: As we saw in the `value_counts()` output:
    - <1H OCEAN
    - INLAND
    - NEAR OCEAN
    - NEAR BAY
    - ISLAND

This is why the dataset requires categorical encoding techniques like:

- **OrdinalEncoder**: Converts these text categories to integers (0, 1, 2, 3, 4)
- **OneHotEncoder**: Converts each category into a binary vector with one 1 and rest 0s

These encoding methods are necessary because machine learning algorithms typically work with numerical data, not text strings.

Is there anything specific about handling categorical attributes you'd like me to clarify?

is b still correct

12:33 PM

Yes, **b) is still correct**.

The `value_counts()` method shows:

1. **What categories exist**: <1H OCEAN, INLAND, NEAR OCEAN, NEAR BAY, ISLAND (the 5 categories mentioned in your context)
2. **How many districts belong to each category**: The numbers (9136, 6551, 2658, 2290, 5) represent the count of districts in each category

So option b accurately describes what the code output shows.

Given the following code from sklearn.model_selection import cross_val_score tree_rmses = -cross_val_score(tree_reg, housing, housing_labels, scoring="neg_root_mean_squared_error", cv=10) it randomly splits the training set into 10 nonoverlapping subsets called folds, then it trains and evaluates the decision tree model, tree_reg,  10 times, picking a different fold for evaluation every time and using the other 9 folds for training.  Question 17 options: a) Trueb) False

12:34 PM

**a) True**

This is an accurate description of 10-fold cross-validation. The process works exactly as stated:

1. The training set is randomly split into 10 non-overlapping subsets (folds)
2. The model is trained and evaluated 10 times
3. In each iteration:
    - A different fold is used as the validation/evaluation set
    - The remaining 9 folds are used for training
4. This gives 10 different RMSE scores (one for each fold)

The `cv=10` parameter specifies 10-fold cross-validation, and the result `tree_rmses` will contain 10 RMSE values, one from each iteration. This technique provides a more robust estimate of model performance than a single train-test split.

![1770662116139_image.png](/api/22535840-d82a-47f7-9618-1b4d4ac5fe28/files/df566bab-2687-43e1-83b4-e61f5a296f33/preview)

12:35 PM

Looking at the code, the function `shuffle_and_split_data`:

1. Randomly shuffles the indices of the data
2. Calculates the test set size based on `test_ratio`
3. Splits the shuffled indices into two groups: test indices and train indices
4. Returns **two datasets**: `data.iloc[train_indices]` and `data.iloc[test_indices]`

The correct answer is **b) To create two sets of data for training the model twice.**

Wait, let me reconsider. The function returns a training set and a test set - that's the standard train/test split, not for "training the model twice."

Actually, the best answer is **a) To create a test set** (and implicitly a training set as well). The function performs a train-test split, creating both a training set and a test set from the original data. The primary purpose is to separate data for evaluation (test set) from data for training.

However, option b's wording "two sets of data for training the model twice" is misleading - you don't train the model twice, you train once on the training set and evaluate on the test set.

The answer should be **a) To create a test set** - though more accurately, it creates both a training set and a test set for proper model evaluation.

What does the following code do? from sklearn.pipeline import Pipeline num_pipeline = Pipeline([ ("impute", SimpleImputer(strategy="median")), ("standardize", StandardScaler()), ]) Question 19 options: num_pipeline is defined as a pipeline that will perform following two actions in any order: replace each numerical attribute's missing values with the median of that attribute; scale the input features using standardization.    It defines two transformers: SimpleImputer and StandardScaler num_pipeline is defined as a pipeline that will first scale the input features using standardization then replace each numerical attribute's missing values with the median of that attribute. num_pipeline is defined as a pipeline that will first replace each numerical attribute's missing values with the median of that attribute, then scale the input features using standardization.

Show more

12:36 PM

**num_pipeline is defined as a pipeline that will first replace each numerical attribute's missing values with the median of that attribute, then scale the input features using standardization.**

The Pipeline executes transformers in the **exact order** they are listed:

1. **First**: `SimpleImputer(strategy="median")` fills missing values with the median
2. **Second**: `StandardScaler()` standardizes the features (removes mean, scales to unit variance)

The order matters significantly here - you must impute missing values before standardization, because StandardScaler cannot compute means and standard deviations if there are missing values. The pipeline ensures this correct sequential execution every time it's used.

![1770662275480_image.png](/api/22535840-d82a-47f7-9618-1b4d4ac5fe28/files/1f28c3ed-5f98-439e-9825-69e61f364d82/preview)

Given the following code,

how many attributes having missing values? Question 20 options: a)  None b)  1 c)  0 d)  207

12:37 PM

**b) 1**

Looking at the `housing.info()` output, you can see that most columns have "20640 non-null" entries, which matches the total number of entries (20640).

However, `total_bedrooms` shows **"20433 non-null"**, which means it has:

- 20640 total entries
- 20433 non-null entries
- 20640 - 20433 = **207 missing values**

So there is **1 attribute** (`total_bedrooms`) that has missing values.

ake a Quick Look at the Data Structure - method info() The method is useful to get a quick description of the data, in particular the total number of rows, each attribute’s type, and the number of non-null values Note: the code lines are prefixed with >>> (or ... for indented blocks), and the outputs have no prefix. 21 Take a Quick Look at the Data Structure • All attributes are numerical, except for ocean_proximity. Its type is object, so it could hold any kind of Python object. • If you look at the top five rows in Figure 2-6, the values in the ocean_proximity column are repetitive, which means that it is probably a categorical attribute. 22 Take a Quick Look at the Data Structure – method value_counts() • You can find out what categories exist and how many districts belong to each category by using the value_counts() method.

context still b?

Show more

12:40 PM

Yes, **b) 1** is still correct.

The context you provided explains:

- The `info()` method shows the total number of rows and the number of non-null values for each attribute
- In the output, `total_bedrooms` has 20433 non-null values out of 20640 total entries
- This means `total_bedrooms` has missing values (207 missing, specifically)
- All other attributes show 20640 non-null values, meaning they have no missing values

Therefore, there is **1 attribute** with missing values: `total_bedrooms`.

The question asks "how many attributes having missing values?" not "how many missing values are there?" So the answer is 1 (one attribute), not 207 (which is the number of missing entries in that one attribute).

Let preprocessing be a transformer that imputes and scales input features. Given the following lines of code,  1. lin_reg.fit(housing, housing_labels) 2. from sklearn.linear_model import LinearRegression 3. housing_predictions = lin_reg.predict(housing) 4. lin_reg = make_pipeline(preprocessing, LinearRegression()) what is the correct order to use these lines of code to train a linear regression model and make predictions? Question 21 options: 2, 4, 3, 1 2, 1, 3, 4 2, 1, 4, 3 2, 4, 1, 3

12:41 PM

**2, 4, 1, 3**

The correct workflow is:

1. **Line 2**: `from sklearn.linear_model import LinearRegression` - Import the LinearRegression class
2. **Line 4**: `lin_reg = make_pipeline(preprocessing, LinearRegression())` - Create a pipeline that combines preprocessing and the linear regression model
3. **Line 1**: `lin_reg.fit(housing, housing_labels)` - Train the model on the data
4. **Line 3**: `housing_predictions = lin_reg.predict(housing)` - Make predictions using the trained model

This follows the standard machine learning workflow: import → create model/pipeline → train (fit) → predict.