Data analysis is a much sought after skill for data science. In my search for efficient tools for analyzing data, after outgrowing spreadsheets, I came across other tools like R's tidyverse but discovering pandas was a game changer. 

pandas is hardly used alone and mostly use alongside numerical computing tools like NumPy and Scipy and visualization tools like matplotlib or seaborn. pandas is closely associated with NumPy as it adopts certain aspects of NumPy's array-based computing like array-based functions and vectorization (basically eliminating for loops in Python). 

Comparing NumPy and pandas, I'll say the biggest difference is that while pandas work with tabular data in rows and columns (which can be heterogeneous), NumPy is most suited for homogeneous numerical array data that is usually typed.

Pandas is a super popular library for fast and convenient data analysis built on top of the Python programming language, that provides two data structures for data manipulation:
1. Series
2. DataFrames

A series is a one dimensional array of indexed data that consists of an array of actual data and an associated array of indices or labels. 

A DataFrame on the other hand is a two dimensional data structure. The data is usually tabular and arranged in rows and columns. A DataFrame can be created from lists, dictionaries or lists of dictionaries. It can also be created by loading data from storage like csv files, SQL database, excel files etc. 

The index (of pandas Series or DataFrame) is used to access individual data values. A column of a dataframe can also be accessed as a Series. A pandas series is for all intents and purposes a 1-D dataframe.

To illustrate some of the concepts already mentioned, it is necessary to import pandas. In this article, it is assumed that the individual already has Python and pandas installed.
Importing pandas is usually done usng the syntax below:
```py
import pandas as pd

```
Since pandas is hardly used alone, the following is a more realistic import:

```py
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```
In addition, since the Series and DataFrame functions will most likely be frequently used, they can be imported as below:

```py
from pandas import Series, DataFrame
```

### Creating pandas series and DataFrames
Here I will briefly provide the syntax for creating pandas series and DataFrame objects. 
To create a pandas series object, the following can suffice:
```py
obj = Series([4,7,-5,3])
obj

```
The output will be as follows:
```
0    4
1    7
2   -5
3    3
dtype: int64
```
To create a DataFrame from a dictionary:
```py
#Define the dictionary 'x'

x = {'Name': ['Lukman','Aminu', 'Amina', 'Fatima'], 'ID': [1, 2, 3, 4], 'Department': ['Architect Group', 'Software Group', 'Design Team', 'Infrastructure'], 
      'Salary':[100000, 80000, 50000, 60000]}

#casting the dictionary to a DataFrame
df = pd.DataFrame(x)

#display the result df
df
```
The output will be:
```
	Name	ID	Department	Salary
0	Lukman	1	Architect Group	100000
1	Aminu	2	Software Group	80000
2	Amina	3	Design Team	50000
3	Fatima	4	Infrastructure	60000
```
There's a direct correspondence between the table and the dictionary. The keys correspond to the column labels and the values or lists corresponding to the rows.
DataFrames can also be created from lists, lists of lists or loaded from storage:
```py
df = pd.read_csv('example.csv')
```
The advantage of loading from storage is that there wont be a need to type in the data and it supports working on large datasets. 

I will concentrate more on manipulating DataFrames. 

### Column selection in pandas dataframes
Columns can be selected using two different notations:
1. df['columnname.]: returns a series: or df[['columnname']]: returns a DataFrame
2. df.columnname 
The second notation only works if the columnname is a valid Python variable. 

Multiple columns can be accessed by passing the list of columns as follows:
```py
df[['Name','ID']]
```
### Using loc and iloc functions for selecting ranges in a DataFrame
loc() is a label-based data selecting method which means that we have to pass the name of the row or column that we want to select. This method includes the last element of the range passed in it.

The syntax can be simplified below:
```py
loc[row_label, column_label]
```
iloc() is an indexed-based selecting method which means that we have to pass integer index in the method to select a specific row/column. This method does not include the last element of the range passed in it.

The syntax can be simplified below:
```py
iloc[row_index, column_index]
```
### Performing arithmetic on pandas DataFrames
pandas allows for easy arithmetic on DataFrames with different labels by providing the union of the dataframes. 
For example:
```py
df1 = pd.DataFrame(np.arange(9.).reshape((3, 3)), columns=list("bcd"),
                      index=["Kaduna", "Kano", "Katsina"])

df2 = pd.DataFrame(np.arange(12.).reshape((4, 3)), columns=list("bde"),
                      index=["Sokoto", "Kano", "Kaduna", "Kebbi"])
print(df1,'\n')
print(df2)
```
Output:
```
           b    c    d
Kaduna   0.0  1.0  2.0
Kano     3.0  4.0  5.0
Katsina  6.0  7.0  8.0 

          b     d     e
Sokoto  0.0   1.0   2.0
Kano    3.0   4.0   5.0
Kaduna  6.0   7.0   8.0
Kebbi   9.0  10.0  11.0
```
The beauty of pandas is that it aligns on both the rows and columns and provide the sum for where the rows or columns appear in both DataFrames and returns NA for those that are not in both as shown below:
```py
df1 + df2
```
Output:
```
	b	c	d	e
Kaduna	6.0	NaN	9.0	NaN
Kano	6.0	NaN	9.0	NaN
Katsina	NaN	NaN	NaN	NaN
Kebbi	NaN	NaN	NaN	NaN
Sokoto	NaN	NaN	NaN	NaN
```
In addition, pandas has some flexible arithmetic methods for calculations in DataFrames and series. These include:
1. add, radd
2. sub, rsub
3. div, rdiv etc

Operations between DataFrames and series are also supported, just like broadcasting in NumPy.

### Computing descriptive statistics
pandas objects have built-in methods for computing descriptive statistics on DataFrames and series. For instance:
-  Calling DataFrame’s sum method returns a Series containing column sums, passing axis="columns" or axis=1 sums across the columns instead:


```py
df.sum()

df.sum(axis=1)
```

- Same can be done to get the column means or row means (axis = 1):


```py
df.mean()
```

- Describe method produces multiple summary statistics all at once for all the columns

```py
df.describe()
```

There are various other methods for obtaining specific summary statistics in a DataFrame. The aim here is just to provide a taste of the possibilities, as with my NumPy article.

In conclusion, pandas is a powerful library with useful tools for data analysis and in this article, I attempted to provide a glimpse of what can be achieved with pandas. The pandas documentation is a useful resource alongside an individual's inquisitiveness and willingness to explore different datasets using pandas. In addition, I found Python for Data Analysis by Wes McKinney quite useful as it gave an intuition into data analysis with Python. 
