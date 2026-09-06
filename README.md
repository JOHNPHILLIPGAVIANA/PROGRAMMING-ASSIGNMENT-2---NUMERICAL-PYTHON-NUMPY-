# PROGRAMMING ASSIGNMENT 2 - NUMERICAL PYTHON (NUMPY)
## Gaviana, John Phillip V.
## 2ECE-A
This repository contains the Python program and readme file for Programming Assignment 2 - Numerical Python (NUMPY). 

## Python Program and Explanation
This loads the Numpy Library and makes the codes available for use
```python
import numpy as np
```

# A. Reproducible Normalization Problem
The Python Program below shows how a character of a string is interchanged in position while keeping all other remaining characters in to their respective orders.
## Python Program and Explanation
```python
np.random.seed(2112) #Creates a reproducible random 5x5 integer ndarray named X
X = np.random.randint(10, 101, size=(5, 5)) #Creates a reproducible random 5x5 integer ndarray named X

x_bar = X.mean() #Computes for the Mean
sigma = X.std() #Computes for the Standard Deviation
X_normalized = (X - x_bar)/sigma #Normalizes the Array

#Prints and Displays the Outputs of the Array
print("Array X:\n", X)
print("\nArray X_normalized:\n", X_normalized)
print("\nMean of X_normalized:", X_normalized.mean())
print("Standard Deviation of X_normalized:", X_normalized.std())

np.save("X_normalized.npy", X_normalized) #Saves the Normalized Array
```








# B. Cubes Divisible by 4 Problem
The Python Program below shows how basic strings methods and string concatenation are used in building a username.
## Python Program and Explanation
```python
C = (np.arange(1, 101) ** 3).reshape(10,10) #Creates the first 100 positive integers, cubes every element, and reshapes the result into a 10x10 ndarray named C.

div_by_4 = C[C % 4 == 0] #Extract all elements from C that are divisible by 4 using Boolean indexing

#Prints and Displays the Outputs of the Array
print("Shape of C:", C.shape)
print("\nArray div_by_4:\n", div_by_4)
print("\nNumber of Selected Elements:", div_by_4.size)

np.save("div_by_4.npy", div_by_4) #Saves the Selected Array
```









# C. Above-Mean Squares Problem
The Python Program below unpacks a sequence and returns a new list in which the first and last elements have exchanged positions.
## Python Program and Explanation
```python
S = (np.arange(1, 37) ** 2).reshape(6,6) #Creates a 6x6 ndarray named S that contains the squares of the first 36 positive integers in an increasing row-major order.

S_mean = S.mean() #Computes for the Mean of S

above_mean = S[S > S_mean] #Uses Boolean Filtering to extract only the elements strictly greater than S_mean

#Prints and Displays the Outputs of the Array
print("Array S: \n", S)
print("\nMean of S (S_mean):", S_mean)
print("\nArray above_mean:\n", above_mean)
print("\nNumber of Selected Elements:", above_mean.size)

np.save("above_mean.npy", above_mean) #Saves the Selected Array
```
