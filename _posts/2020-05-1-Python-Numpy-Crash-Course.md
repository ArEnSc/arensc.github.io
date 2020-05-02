---
layout: post 
title: Numpy Top Functions used in Data Analysis
tags: [Numpy, Python, Notes]
feature-img: "assets/img/matplotlib-charts.jpg"
thumbnail: "assets/img/matplotlib-charts.jpg"
excerpt_separator: <!--more-->
---

Numpy Top Functions used in Data Analysis

<!--more-->

Top Functions

```python
# To add a new cell, type '# %%'
# To add a new markdown cell, type '# %% [markdown]'
# %%
import numpy as np


# %%
# Numpy The commonly used Functions Memorize these


# %%
# Initialize an array from a list
my_list = [1,2,3,3]
x = np.array(my_list)


# %%
# if you need to check the type
type(x)


# %%
# Create a matrix from an array
my_matrix = [
    [1,2,3],
    [4,5,6],
    [7,8,9]]


# %%
print(my_matrix)


# %%
# Use the same initializer
np.array(my_matrix)


# %%
# Create a range from 0 -> 5
list(range(0,5))


# %%
# Create a range with space inbetween
list(range(0,10,2))


# %%
# Easier way use a range
print(np.arange(0,100,2))


# %%
# An array of zeroes rows by columns
np.zeros((2,3))


# %%
# An array of ones
np.ones((10,10))


# %%
# This gives us numbers from 0 to 10, with 100 elements evenly spaced between them
np.linspace(0,10,100)


# %%
# identity matrix 
np.eye(10,10)


# %%
# Random Library! want a random set of numbers gives us a random numbers between 0-1 using a uniforn distribution
# meaning a from 0-1 each number is picked randomly given probability. 
np.random.rand(5,5)


# %%
# Closer you are the mean the higher likely hood you are picked as a number
np.random.randn(5,5)


# %%
# How about a random integer between two values, not including 100 give me 10
np.random.randint(0,100,10)


# %%
# reshape in to 5 by 5 matrix
arr = np.arange(25)
arr.reshape(5,5) # quick trick for reshaping 5,5 must equal 25


# %%
# Max number gives you the max number
arr.max() 
# Arg Max gives you the argument of the max, same with min and max
arr.argmax()
# Gives you the type of the array
arr.dtype


# %%



# %%




```

