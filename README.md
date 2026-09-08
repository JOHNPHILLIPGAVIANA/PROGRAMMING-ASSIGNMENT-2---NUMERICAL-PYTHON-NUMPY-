# PROGRAMMING ASSIGNMENT 2 - NUMERICAL PYTHON (NUMPY)
## Gaviana, John Phillip V.
## 2ECE-A
This repository contains the Python program and readme file for Programming Assignment 2 - Numerical Python (NumPy). 

## Python Program and Explanation
```python
import numpy as np
```
This loads the Numpy Library and makes it available to use for coding.

# A. Reproducible Normalization Problem
The Python program below shows how a 5x5 matrix of random integers is generated and normalized using Z-score calculation to produce a distribution centered at zero.
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
### 1. Array Generation (`np.random.seed`, `randint`)
**Purpose:** Creates a reproducible array of random integers. Executing `np.random.seed(2112)` fixes the random number generator's initial state, while `np.random.randint(10, 101, size=(5, 5))` generates a 5x5 matrix X filled with integer values in the range of 10 to 100.
### 2. Parameter Calculation and Scaling (`X.mean()`, `X.std()`, `X_normalized`)
**Purpose:** The operations perform standard score feature scaling. The methods `X.mean()` and `X.std()` compute the mean (x̄) and standard deviation (σ) of the raw array, respectively. The mathematical expression `(X - x_bar)/sigma` centers the matrix values around zero and scales them to unit variance, storing the scaled matrix in `X_normalized`.
### 3. Output Display & File Saving (`print`, `np.save`) 
**Purpose:** Running `.mean()` and `.std()` on `X_normalized` verifies successful normalization, yielding a mean of 0.0 and standard deviation of 1.0. The statement `np.save("X_normalized.npy", X_normalized)` writes the processed matrix to an external file using NumPy binary format.

# B. Cubes Divisible by 4 Problem
The Python program below demonstrates how a 10x10 matrix of cubed numbers is constructed and filtered using Boolean indexing to extract elements that are evenly divisible by 4.
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
### 1. Array Generation and Reshaping (`np.arange`, `** 3`, `reshape`)
**Purpose:**  Generates and constructs a 10x10 ndarray named C. The function `np.arange(1, 101)` produces a sequence of positive integers from 1 to 100, the exponent operator `** 3` raises each value to its cube, and `.reshape(10,10)` transforms the 100-element vector into a two-dimensional grid.
### 2. Boolean Indexing and Filtering (`C[C % 4 == 0]`)
**Purpose:** Extracts all elements from the array C that are divisible by 4. The logical condition `C % 4 == 0` generates a boolean mask that evaluates to True for elements with a remainder of zero, filtering out non-qualifying values and flattening the result into a 1D array named `div_by_4`.
### 3. Output Display & File Saving (`print`, `.shape`, `.size`, `np.save`)
**Purpose:** Verifies the array attributes and saves the filtered output. Outputting `C.shape` confirms the grid dimensions (10, 10), while `div_by_4.size` computes the total count of selected elements (50). Lastly, `np.save("div_by_4.npy", div_by_4)` writes the filtered array to an external file using NumPy binary format.

# C. Above-Mean Squares Problem
The Python program below illustrates how a 6x6 matrix of squared integers is analyzed to compute its mean and extract all values strictly greater than that average.
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
### 1. Array Generation and Reshaping (`np.arange`, `** 2`, `reshape`)
**Purpose:**  Generates and constructs a 6x6 ndarray named as S. The function `np.arange(1, 37)` generates an array containing the first 36 positive integers, `** 2` squares each value individually, and `.reshape(6,6)` arranges the elements into a two-dimensional grid in row-major order.
### 2. Statistical Mean and Boolean Filtering (`S.mean()`, `S[S > S_mean]`)
**Purpose:** The operations compute the selection threshold and extract matching values. The method `S.mean()` calculates the arithmetic mean of all elements in the matrix, storing it in `S_mean`. The expression `S[S > S_mean]` applies conditional masking to extract only the values strictly greater than `S_mean`, returning them as a 1D array named `above_mean`.
### 3. Output Display & File Saving (`print`, `.size`, `np.save`)
**Purpose:** Displays the output or calculated data as the result. Outputting `above_mean.size` determines the total count of filtered elements (15). Lastly, `np.save("above_mean.npy", above_mean)` exports the extracted array to an external file using NumPy binary format.
