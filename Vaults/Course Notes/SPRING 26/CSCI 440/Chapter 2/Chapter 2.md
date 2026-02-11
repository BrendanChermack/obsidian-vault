## Main steps of machine learning project
1. Look at big picture
2. get the data
3. explore and visualize the data to gain insights
4. prepare the data for machine learning algos
5. select a model and train it
6. present solution
7. launch, monitor and maintain your system
## Problem to solve
- use California census data to build a model of housing prices in the state
## Data to use
- The california Housing prices dataset from the statlib repo
- This dataset is based on data from the 1990 california census
- It is not exactly recent but it has many qualities for learning, so we will pretend it is recent data
## Working with real data
- Popular open data repos
	- openMl.org
	- kaggle.com
	- paperswithcode.com
	- UC Irvine machine learning repo
	- Amaon's AWS datasetsTensorflow datasets
- Meta portals (they list open data repo)
	- dataportal.org
	- OpenDataMonitor.eu
- Other pages listing many popular open data repos
	- wikipedia's list of machine learning datasets
	- quora.com
	- the datasets subreddit
## 1st question: the objective of the project
- model's ouput( predition of a disctrict's median housing price) will be fed to another machine learning system, along with many other signals
## 2nd question: current solution
- the current situation will often give you reference for performance as well as insights on how to solve the problem
- current solution
	- the district housing prices are currently estimated manually by experts: a team gathers up to date ingo about a district, and when they cannot get the median housing price they estimate it using complex rules
## design the system
- typical supervised learning task
	- the model can be trained with labeled examples (each instance comes with the expected output)
- typical regression task
	- the model will be asked to predict a value
	- more specifically this is a muliple regression problem
		- since the system will use mulitple features to make a prediction (the districts population, the median, income, etc.)
- it is also a univariate regression problem
		- since we are only trying to a single value for each district. if we were trying predict multiple values per district it would be a multivariate regression problem
- plain batch learning
	- there is no continuous flow of data coming into the system, there is no particular need to adjust changing data rapidly and the data is small enough to fit in memory
## performance measure - RMSE
- a typical performance measure for regression problems is the **root mean square error** 
	- ![[{E9308C95-D7D5-4281-9B18-72CD695761E4}.png]]
- m: the number of instances in the dataset you are measuring the RMSE on
- x^i: a vector of all the feature values (excluding the label) of the ith instance in the dataset, and y^i is its label (the desired output value for the instance)
- h: the system's predication function also called a hypothesis
- RMSE(X,h) is the cost function measured on the set of examples using your hypothesis h.
- X is a matrix containing all the feature values (excluding labels) of all isntances in the dataset. There is one row per instance, and the ith row is equal to the transpose x^i, noted(x^i)t
	- ![[{B042D2D5-753C-4859-A4F1-4D7A8A7AF1D6}.png]]
## performance measure - MAE
- **Mean absolute error** (MAE, also called the average absolute deviation), 
	- ![[{14AB661D-6984-4C6F-BC9A-B504CD85785E}.png]]
- Both the RMSE and the MAE are ways to measure the distance between two vectors: the vector of prediction and the vector of target values
## Check the assumptions
- Lastly, it is good to list and verify the assumptions that have been made so fat (by you or others) this can help you catch serious issues early on.
- you don't want to find a problem after working on your system for months
## running the code examples using Google Colab
- All the code examples in this book are open source and available online as Jupyter notebooks, which are interactive docs
- containing text, image, and exe code snippets (python in our case)
- running the code examples using google Colab
- Read the textbook page 46 ~ 50 about how to use google colab
## download the data
- ```python
from pathlib import Path
import pandas as pd
import tarfile
import urllib.request

def load_housing_data():
    tarball_path = Path("datasets/housing.tgz")
    if not tarball_path.is_file():
        Path("datasets").mkdir(parents=True, exist_ok=True)
        url = "https://github.com/ageron/data/raw/main/housing.tgz"
        urllib.request.urlretrieve(url, tarball_path)
        with tarfile.open(tarball_path) as housing_tarball:
            housing_tarball.extractall(path="datasets")
    return pd.read_csv(Path("datasets/housing.csv"))

housing = load_housing_data()
  ```
## about function load_housing_data()
- when it is called
	- it looks for the dataset file
	- if it doesn't find it it creates the datasets directory inside the current directory (which is /content by default in colab), download the housing.tgz file from the repo and extracts its content into the datasets directory this creates the datasets/housing directory with the housing.csv file inside it
	- lastly the function loads this csv file into a pandas dataframe obj containing all the data and returns it.
## Pandas Dataframe
- pandas: data manipulation and analysis
	- numerical tables and time series
- dataframe: data struct constructed with rows and columns
- ex:
	- ```python
	  mydict = [{'a': 1, 'b': 2, 'c': 3, 'd': 4},
          {'a': 100, 'b': 200, 'c': 300, 'd': 400},
          {'a': 1000, 'b': 2000, 'c': 3000, 'd': 4000}]
	  df = pd.DataFrame(mydict)
      df
	  ```
## Take a quick look at the data structure
- you start by looking at the top 5 rows of data using the Datafrme's head() method
	- ![[{10F16A63-D48C-48CB-A3C8-AD6998877D40}.png]]
## Take a quick look at the data structure - Method info()
- used to get a quick description of the data 
	- total number of rows, each attribute's type, and the number of non-null values
- ![[{DE00F2C6-F4BA-4E25-99D6-BFCE110BEBEC}.png]]
- all attributes are numerical except for ocean_proximity. its type is obj, so it could hold any kind of python obj
- the top 5 rows in the column are reptitive which means that it is probably a categorical attribute
	- ![[{460BBB26-CFFA-4D7C-8092-ECAA8AFDAC58}.png]]
## Take a quick look at the data structure - Method describe()
- ![[{A65E5E7B-A3F6-4FF6-9A2E-6E439E10E877}.png]]
## Take a Quick Look at the Data  Structure – histogram
- another quick way to get the type of data you are dealing with is to plot a histogram for each numerical attribute
- a **histogram** how's the number of instances (on the vert axis) that have a given value range (on horizontal axis)
- you can either plot this one attribute at a time or call the hist()
- the hist() method on the whole dataset plots a histogram for each numerical attribute
- ```python
	import matplotlib.pyplot as plt

	housing.hist(bins=50, figsize=(12, 8))
	plt.show()
  ```
![[{897B4707-E22D-4839-AF36-EB4B99821C3C}.png]]
- if labels (target attributes) were capped, two options:
- collect proper labels for the districts whose labels were capped
- remove those districts from the training set and test set since the system should not be evaluated poorly if it predicts values beyond $500,000
## Create a Test Set
- creating a test set is theoretically simple; pick some instance randomly, typically 20% of the dataset (or less if your dataset is very large) and set them aside
- ```python
  import numpy as np

	def shuffle_and_split_data(data, test_ratio):
	    shuffled_indices = np.random.permutation(len(data))
	    test_set_size = int(len(data) * test_ratio)
	    test_indices = shuffled_indices[:test_set_size]
	    train_indices = shuffled_indices[test_set_size:]
	    return data.iloc[train_indices], data.iloc[test_indices]
  ```
## NUMPY Library function numpy random.permutation()
- random.permutation(x)
	- randomly permute a sequence or return a permuted range
	- if x is multi-dimmesional array, it is only shuffled along its first index
- params
	- x - int or array like
	- if x is an int, randomly permute np.arange(x)
	- if x is an array  make a copy and shuffle the elements randomly
- returns
	- out - ndarray
- examples in the docs
## python List slicing
- returns a portion of an array
- arr[Initial: end: indexjump]
## pandas.DataFrame.iloc
- Purely integer-location based indexing for selection by position
- **.iloc[]** is primarily integer position based (from 0 to length-1 of the axis)
- allowed inputs are:
	- an integer, e.g. 5
	- an list or array of integers e.g. [4,3,0]
	- a slice object with ints e.g. 1:7
	- a boolean array
## Create a Test set
- you can then use the function 
	- ```python
	train_set, test_set = shuffle_and_split_data(housing, 0.2)
	len(train_set)
	16512
	len(test_set)
	4128
	  ```
- This works, but if you run the program again, it will generate a different test set
	- one solution is to save the test set on the first run and then load it in subsequent runs
	- another option is to set the random number generator's seed (e.g., with np.random.seed(42)) before calling np.random.permutation() so that it always generates the same shuffled indices
	- however both these solutions will break the next time you fetch an updated dataset
- solution to have a stable train.test split even after updating the dataset
	- use each instance's identifier to decide whether or not it should go to the test set (assuming instances have unique and immutable id's)
		- example: you could compute a hash of each instance's id and put that instance in the test set if the hash is lower than or equal to 20% of the maximum hash value
			- This ensures that the test set will remain consistent across multiple runs, even if you refresh the dataset. the new test set will contain 20% of the new instances, but it will not contain any instance that was previously in the training set
- ```python
  from zlib import crc32

def is_id_in_test_set(identifier, test_ratio):
    return crc32(np.int64(identifier)) < test_ratio * 2**32

def split_data_with_id_hash(data, test_ratio, id_column):
    ids = data[id_column]
    in_test_set = ids.apply(lambda id_: is_id_in_test_set(id_, test_ratio))
    return data.loc[~in_test_set], data.loc[in_test_set]
  ```
## pandas.DataFrame.apply and lambda functions
- apply()
	- lets you apply custom function to each row/column of a DataFrame or to each element of a Series 
	- ```python
	  DataFrame.apply(func, axis=0)
	  ```
	- axis=0 apply to each column
	- axis=1 apply to each row
- python lambda:
	- a lambda function can take any number of arguments but can only have one expression
## Create a test set
- the housing data set does not have an id column
- the simples solution is to use the row index as the ID:
- ```python
housing_with_id = housing.reset_index()  # adds an 'index' column
train_set, test_set = split_data_with_id_hash(housing_with_id, 0.2, "index")
  ```
- if you use the row index as a unique id, you need to make sure that new data get appended to the end of the dataset and that no row ever gets deleted
- if this is not possible you can try to use the most stable features to build a unique id
	- For example, a district’s latitude and longitude are guaranteed to be stable for a few million years, so you could combine them into an ID like so
	- ```python
	housing_with_id["id"] = housing["longitude"] * 1000 + housing["latitude"]
	train_set, test_set = split_data_with_id_hash(housing_with_id, 0.2, "id")
	  ```
- split datasets into multiple subsets
	- scikit-learn provides a few functions to split datasets into multiple subsets in various ways
		- shuffle_and_split_data() - defined earlier
		- train_test_split()
			- first there is a random_state params that allow you to set the random generator seed
			- second you can pass it multiple datasets with an id number of rows and it will split them on the same indices
		- ```python
		  from sklearn.model_selection import train_test_split
        
        train_set, test_set = train_test_split(housing, test_size=0.2, random_state=42)
		  ```
- Data set (ex. the population) is divided into homogeneous subgroups called **strata** and the right number of instance are sampled from each stratum to guarantee that the test set is representative of the overall population
	- you may want to ensure that the test set is representative of the various categories of income in the whole dataset
- it is important to have sufficient number of instances in your dataset for each stratum or else the estimate of stratum's importance may be biased. This mean that you should not have too many strata, and each stratum should be large enough
- let's look at the median indome histogram more closely most median income values are clustered around 1.5 to 6 (15k to 60k) but some median incomes go far beyond 6
- the following code uses the function pd.cut() to create an income to create an income category attribute with 5 categories from 1 to 5 category 1 ranges from 0 to 1.5 (i.e., less than $15,000), category 2 from 1.5 to 3, and so on:
- ```python 
  housing["income_cat"] = pd.cut(housing["median_income"],
                                        bins=[0., 1.5, 3.0, 4.5, 6., np.inf],
                                        labels=[1, 2, 3, 4, 5])
  ```
- ![[{23440110-CC69-4408-8966-A9E04103443D}.png]]
- ```python
  housing["income_cat"].value_counts().sort_index().plot.bar(rot=0, grid=True)
        plt.xlabel("Income category")
        plt.ylabel("Number of districts")
        plt.show()
  ```
- Now you are ready to do stratified sampling based on the income category
- scikit-learn provides a number of splitter classes in the sklearn.model_selection that implements various strats to split your dataset into a training set and a test set
- each splitter has a split method that returns an iterator over different training/test splits of the same data
- .split() method yields the training and test indices not the data itself
	- for example
	- ```python
		from sklearn.model_selection import StratifiedShuffleSplit
        
	    splitter = StratifiedShuffleSplit(n_splits=10, test_size=0.2, random_state=42)
        strat_splits = []
        for train_index, test_index in splitter.split(housing, housing["income_cat"]):
            strat_train_set_n = housing.iloc[train_index]
            strat_test_set_n = housing.iloc[test_index]
            strat_splits.append([strat_train_set_n, strat_test_set_n])
            
	  ```
- for now you can just use the first split:
- stray_train_set, strat_test_set = strat_split[0]
- or since statified sampling is common theres a shorter way to get a single split using train_test_split() with the statify arg
- ```python
  strat_train_set, strat_test_set = train_test_split(
            housing, test_size=0.2, stratify=housing["income_cat"], random_state=42)
  ```
- 