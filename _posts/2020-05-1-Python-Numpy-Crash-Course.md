---
layout: post 
title: Python VirtualEnv
tags: [VirtualEnv, Python, Notes]
feature-img: "assets/img/matplotlib-charts.jpg"
thumbnail: "assets/img/matplotlib-charts.jpg"
excerpt_separator: <!--more-->
---

Numpy Top Functions used in Data Analysis

<!--more-->

Top Functions

```jupyter
{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "metadata": {},
   "outputs": [],
   "source": [
    "import numpy as np"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Numpy The commonly used Functions"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": "[1 2 3 3]\n"
    }
   ],
   "source": [
    "# Initialize an array from a list\n",
    "my_list = [1,2,3,3]\n",
    "x = np.array(my_list)\n",
    "print(x)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "numpy.ndarray"
     },
     "metadata": {},
     "execution_count": 4
    }
   ],
   "source": [
    "# if you need to check the type\n",
    "type(x)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "metadata": {},
   "outputs": [],
   "source": [
    "# Create a matrix from an array\n",
    "my_matrix = [\n",
    "    [1,2,3],\n",
    "    [4,5,6],\n",
    "    [7,8,9]]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": "[[1, 2, 3], [4, 5, 6], [7, 8, 9]]\n"
    }
   ],
   "source": [
    "print(my_matrix)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "array([[1, 2, 3],\n       [4, 5, 6],\n       [7, 8, 9]])"
     },
     "metadata": {},
     "execution_count": 8
    }
   ],
   "source": [
    "# Use the same initializer\n",
    "np.array(my_matrix)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "[0, 1, 2, 3, 4]"
     },
     "metadata": {},
     "execution_count": 10
    }
   ],
   "source": [
    "# Create a range from 0 -> 5\n",
    "list(range(0,5))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 11,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "[0, 2, 4, 6, 8]"
     },
     "metadata": {},
     "execution_count": 11
    }
   ],
   "source": [
    "# Create a range with space inbetween\n",
    "list(range(0,10,2))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 12,
   "metadata": {},
   "outputs": [
    {
     "output_type": "stream",
     "name": "stdout",
     "text": "[ 0  2  4  6  8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 42 44 46\n 48 50 52 54 56 58 60 62 64 66 68 70 72 74 76 78 80 82 84 86 88 90 92 94\n 96 98]\n"
    }
   ],
   "source": [
    "# Easier way use a range\n",
    "print(np.arange(0,100,2))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 14,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "array([[0., 0., 0.],\n       [0., 0., 0.]])"
     },
     "metadata": {},
     "execution_count": 14
    }
   ],
   "source": [
    "# An array of zeroes rows by columns\n",
    "np.zeros((2,3))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 15,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "array([[1., 1., 1., 1., 1., 1., 1., 1., 1., 1.],\n       [1., 1., 1., 1., 1., 1., 1., 1., 1., 1.],\n       [1., 1., 1., 1., 1., 1., 1., 1., 1., 1.],\n       [1., 1., 1., 1., 1., 1., 1., 1., 1., 1.],\n       [1., 1., 1., 1., 1., 1., 1., 1., 1., 1.],\n       [1., 1., 1., 1., 1., 1., 1., 1., 1., 1.],\n       [1., 1., 1., 1., 1., 1., 1., 1., 1., 1.],\n       [1., 1., 1., 1., 1., 1., 1., 1., 1., 1.],\n       [1., 1., 1., 1., 1., 1., 1., 1., 1., 1.],\n       [1., 1., 1., 1., 1., 1., 1., 1., 1., 1.]])"
     },
     "metadata": {},
     "execution_count": 15
    }
   ],
   "source": [
    "# An array of ones\n",
    "np.ones((10,10))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 24,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "array([ 0.        ,  0.1010101 ,  0.2020202 ,  0.3030303 ,  0.4040404 ,\n        0.50505051,  0.60606061,  0.70707071,  0.80808081,  0.90909091,\n        1.01010101,  1.11111111,  1.21212121,  1.31313131,  1.41414141,\n        1.51515152,  1.61616162,  1.71717172,  1.81818182,  1.91919192,\n        2.02020202,  2.12121212,  2.22222222,  2.32323232,  2.42424242,\n        2.52525253,  2.62626263,  2.72727273,  2.82828283,  2.92929293,\n        3.03030303,  3.13131313,  3.23232323,  3.33333333,  3.43434343,\n        3.53535354,  3.63636364,  3.73737374,  3.83838384,  3.93939394,\n        4.04040404,  4.14141414,  4.24242424,  4.34343434,  4.44444444,\n        4.54545455,  4.64646465,  4.74747475,  4.84848485,  4.94949495,\n        5.05050505,  5.15151515,  5.25252525,  5.35353535,  5.45454545,\n        5.55555556,  5.65656566,  5.75757576,  5.85858586,  5.95959596,\n        6.06060606,  6.16161616,  6.26262626,  6.36363636,  6.46464646,\n        6.56565657,  6.66666667,  6.76767677,  6.86868687,  6.96969697,\n        7.07070707,  7.17171717,  7.27272727,  7.37373737,  7.47474747,\n        7.57575758,  7.67676768,  7.77777778,  7.87878788,  7.97979798,\n        8.08080808,  8.18181818,  8.28282828,  8.38383838,  8.48484848,\n        8.58585859,  8.68686869,  8.78787879,  8.88888889,  8.98989899,\n        9.09090909,  9.19191919,  9.29292929,  9.39393939,  9.49494949,\n        9.5959596 ,  9.6969697 ,  9.7979798 ,  9.8989899 , 10.        ])"
     },
     "metadata": {},
     "execution_count": 24
    }
   ],
   "source": [
    "# This gives us numbers from 0 to 10, with 100 elements evenly spaced between them\n",
    "np.linspace(0,10,100)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 26,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "array([[1., 0., 0., 0., 0., 0., 0., 0., 0., 0.],\n       [0., 1., 0., 0., 0., 0., 0., 0., 0., 0.],\n       [0., 0., 1., 0., 0., 0., 0., 0., 0., 0.],\n       [0., 0., 0., 1., 0., 0., 0., 0., 0., 0.],\n       [0., 0., 0., 0., 1., 0., 0., 0., 0., 0.],\n       [0., 0., 0., 0., 0., 1., 0., 0., 0., 0.],\n       [0., 0., 0., 0., 0., 0., 1., 0., 0., 0.],\n       [0., 0., 0., 0., 0., 0., 0., 1., 0., 0.],\n       [0., 0., 0., 0., 0., 0., 0., 0., 1., 0.],\n       [0., 0., 0., 0., 0., 0., 0., 0., 0., 1.]])"
     },
     "metadata": {},
     "execution_count": 26
    }
   ],
   "source": [
    " # identity matrix \n",
    " np.eye(10,10)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 28,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "array([[0.31834608, 0.37287197, 0.53972275, 0.96752417, 0.27322676],\n       [0.10657325, 0.51572866, 0.86314127, 0.36632002, 0.66251957],\n       [0.46390197, 0.50152179, 0.98884019, 0.75515769, 0.44100596],\n       [0.80050805, 0.04063533, 0.26323111, 0.10664679, 0.70834863],\n       [0.75127822, 0.10909121, 0.95261083, 0.30269361, 0.12287222]])"
     },
     "metadata": {},
     "execution_count": 28
    }
   ],
   "source": [
    "# Random Library! want a random set of numbers gives us a random numbers between 0-1 using a uniforn distribution\n",
    "# meaning a from 0-1 each number is picked randomly given probability. \n",
    "np.random.rand(5,5)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 30,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "array([[-1.31126185, -1.6725139 , -0.49686186,  0.02229481,  0.25974385],\n       [-0.48363992, -0.85350112,  0.21628953,  0.6383835 ,  0.44286601],\n       [-1.2142946 ,  1.08847682,  0.65954538, -0.71819192,  0.50693687],\n       [ 0.82066027, -0.61314438, -0.42597942, -1.38178588,  1.57186238],\n       [ 0.1800873 , -0.79538297, -1.15445679,  0.0026279 ,  0.15457788]])"
     },
     "metadata": {},
     "execution_count": 30
    }
   ],
   "source": [
    "# Closer you are the mean the higher likely hood you are picked as a number\n",
    "np.random.randn(5,5)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 33,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "array([85, 11, 21, 13, 68, 39,  6, 46, 83, 23])"
     },
     "metadata": {},
     "execution_count": 33
    }
   ],
   "source": [
    "# How about a random integer between two values, not including 100 give me 10\n",
    "np.random.randint(0,100,10)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 36,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "array([[ 0,  1,  2,  3,  4],\n       [ 5,  6,  7,  8,  9],\n       [10, 11, 12, 13, 14],\n       [15, 16, 17, 18, 19],\n       [20, 21, 22, 23, 24]])"
     },
     "metadata": {},
     "execution_count": 36
    }
   ],
   "source": [
    "# reshape in to 5 by 5 matrix\n",
    "arr = np.arange(25)\n",
    "arr.reshape(5,5) # quick trick for reshaping 5,5 must equal 25"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 45,
   "metadata": {},
   "outputs": [
    {
     "output_type": "execute_result",
     "data": {
      "text/plain": "dtype('int64')"
     },
     "metadata": {},
     "execution_count": 45
    }
   ],
   "source": [
    "# Max number gives you the max number\n",
    "arr.max() \n",
    "# Arg Max gives you the argument of the max, same with min and max\n",
    "arr.argmax()\n",
    "# Gives you the type of the array\n",
    "arr.dtype"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.7.5-final"
  },
  "orig_nbformat": 2,
  "kernelspec": {
   "name": "python37564bitquantworkvenv8229207ed069482e988ecddbe0b411a9",
   "display_name": "Python 3.7.5 64-bit ('quantwork': venv)"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}
```

