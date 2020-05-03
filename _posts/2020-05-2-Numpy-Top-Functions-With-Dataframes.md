---
layout: post 
title: Numpy Top Functions used with Dataframes
tags: [Numpy,Pandas, Python, Notes]
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

# A series is a numpy array with labels
series = pd.Series(aList)
print(series)


# %%
seriesLabel = pd.Series(aList,index=labels)
print(seriesLabel)


# %%
seriesWithDict = pd.Series(d)
print(seriesWithDict)


# %%
# Lets create a series
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
# expect that it wouldn't be able to add non existing labels 


# %%
# 2d frame of data
from numpy.random import randn
# all data frame is, is a set of series that shares common index abcde, xyz is the series
dataframe = pd.DataFrame(randn(5,3),['a','b','c','d','e'],['x','y','z'])
print(dataframe)


# %%
# selecting from data frames
dataframe["y"] 


# %%
type(dataframe['x']) # series type


# %%
dataframe[['x','y']] # get two series


# %%
# create a new series in a data frame if you create one that is larger than the axis = 0 or the run along the rows or the labels it will error out
dataframe['newSeries'] = range(0,5)


# %%
print(dataframe['newSeries'])


# %%
dataframe['newSeries'] 


# %%
# lets delete a column or a series you can use the inplace arg to ensure that it modifies it in memory rather than returning a copy
dataframe.drop('newSeries',axis=1)
print(dataframe) # you will see here that the data frame is still availible


# %%
# lets drop a labeled row
dataframe.drop('a',axis=0)


# %%
dataframe.shape


# %%
# rows are also a series as well, this is how to select a row.
dataframe.loc['a']


# %%
# select a row with iloc
dataframe.iloc[0]


# %%
# you can select by each one
dataframe.loc[['d','a']]


# %%
# you can slice
dataframe.loc['a':'e']


# %%
# you can slice via row and col 
dataframe.loc['a':'b',:'z']


# %%

```

