---
layout: post 
title: Numpy Top Functions used with Dataframes
tags: [Numpy, Pandas, Python, Notes]
feature-img: "assets/img/matplotlib-charts.jpg"
thumbnail: "assets/img/matplotlib-charts.jpg"
excerpt_separator: <!--more-->
---

Numpy Top Functions used in Data Analysis

<!--more-->

Top Functions

```python
# %%
import numpy as np
import pandas as pd


# %%
labels = ['a','b','c']
aList = [1,2,3]
array = np.array([1,2,3])
d = {'a':1,'b':2,'c':3}

# A Series is a numpy array with labels
series = pd.Series(aList)
print(series)


# %%
seriesLabel = pd.Series(aList,index=labels)
print(seriesLabel)


# %%
seriesWithDict = pd.Series(d)
print(seriesWithDict)


# %%
# Let's create a series
series1 = pd.Series([1,2,3],index=['Asia','Europe','NorthAmerica'])
print(series1)


# %%
# Access a series via its label
series1["NorthAmerica"]


# %%
# You can add series together
series2 = pd.Series([1,2,3,4],index=['Asia','Europe','NorthAmerica',"NorthUmbria"])
newSeries3 = series1 + series2
print(newSeries3)
# Expect that it wouldn't be able to add non-existing labels 


# %%
# 2D frame of data
from numpy.random import randn
# All a DataFrame is, is a set of series that share common index abcde; xyz are the series
dataframe = pd.DataFrame(randn(5,3),['a','b','c','d','e'],['x','y','z'])
print(dataframe)


# %%
# Selecting from DataFrames
dataframe["y"] 


# %%
type(dataframe['x']) # Series type


# %%
dataframe[['x','y']] # Get two series


# %%
# Create a new series in a DataFrame. If you create one that is larger than axis=0 or runs along the rows or the labels, it will error out
dataframe['newSeries'] = range(0,5)


# %%
print(dataframe['newSeries'])


# %%
dataframe['newSeries'] 


# %%
# Let's delete a column or a series. You can use the inplace arg to ensure that it modifies it in memory rather than returning a copy
dataframe.drop('newSeries',axis=1)
print(dataframe) # You will see here that the DataFrame is still available


# %%
# Let's drop a labeled row
dataframe.drop('a',axis=0)


# %%
dataframe.shape


# %%
# Rows are also a series as well. This is how to select a row.
dataframe.loc['a']


# %%
# Select a row with iloc
dataframe.iloc[0]


# %%
# You can select by each one
dataframe.loc[['d','a']]


# %%
# You can slice
dataframe.loc['a':'e']


# %%
# You can slice via row and col 
dataframe.loc['a':'b',:'z']


# %%

```

