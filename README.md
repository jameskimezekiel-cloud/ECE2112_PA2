# PA2_ECE2112_JAMES, KE
---

### EXPERIMENT 2: NUMERICAL PYTHON (NUMPY)
**Submitted By:** James, Kim Ezekiel G. | 2ECE-A | 09/04/2026

The content of this repository contains the Programming Assignment 1 for our course "Advance Computer Programming" this S.Y. 2025-2026. This project covers three python problems pertaining to Module 1 - Base Computing with Python.

## Objectives
---
##### At the end of this laboratory activity, the student should be able to:
1. create and reshape NumPy arrays using appropriate NumPy functions;
2. perform vectorized numerical operations on an ndarray;
3. compute array statistics and use Boolean conditions to select elements; and
4. save computed NumPy arrays as .npy files.

# EXPERIMENT 2: Numerical Python (NumPy)

**Submitted by:** James, Kim Ezekiel G.
**Section:** 2ECE-A
**Date:** 09/04/2026

## Overview

This notebook (`ADPROG_PA2.ipynb`) contains three NumPy exercises covering array creation, normalization, boolean filtering, and reshaping. Each problem prints the required checks to the console and saves its result as a `.npy` file.

---

## A. Reproducible Normalization Problem

**Task:** Create a reproducible random 5×5 integer ndarray `X` using:
```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
```
Normalize `X` so that the resulting array has a mean of 0 and a standard deviation of 1.

**Output checks:**
- `X` (original array)
- `X_normalized` (normalized array)
- Mean of `X_normalized` → `0.0`
- Standard deviation of `X_normalized` → `0.9999999999999999` (≈ 1, floating-point rounding)

**Saved file:** `X_normalized.npy`

**Code:**
```python
import numpy as np
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))

X_mean = X.mean()
O_std = X.std()

X_normalized = (X - X_mean) / O_std
print("X:")
print(X)

print("\nX_normalized:")
print(X_normalized)

print("\nMean of X_normalized:", X_normalized.mean())
print("Standard deviation of X_normalized:", X_normalized.std())

np.save("X_normalized.npy", X_normalized)
```

---

## B. Cubes Divisible by 4 Problem

**Task:** Create the first 100 positive integers, cube each element, and reshape into a 10×10 ndarray `C` (from 1³ to 100³). Use boolean filtering to select cubes divisible by 4, storing them in `div_by_4`, preserving row-major order.

**Output checks:**
- Shape of `C` → `(10, 10)`
- `div_by_4` array
- Number of selected elements → `50`
- First selected value → `8`
- Last selected value → `1,000,000`

**Saved file:** `div_by_4.npy`

**Code:**
```python
numbers = np.arange(1, 101)

C = numbers**3
C = C.reshape(10, 10)

div_by_4 = C[C % 4 == 0]

print("Shape of C:", C.shape)
print("\ndiv_by_4:")
print(div_by_4)

print("\nNumber of selected elements:", div_by_4.size)

np.save("div_by_4.npy", div_by_4)
```

---

## C. Above-Mean Squares Problem

**Task:** Create a 6×6 ndarray `S` containing the squares of the first 36 positive integers in row-major order. Compute `S_mean`, then use boolean filtering to select elements strictly greater than `S_mean`, storing them in `above_mean`.

**Output checks:**
- `S` (6×6 array of squares)
- `S_mean` → `450.1666666666667`
- `above_mean` array
- Number of selected elements → `15`
- First selected value → `484`
- Last selected value → `1296`

**Saved file:** `above_mean.npy`

**Code:**
```python
S = np.arange(1, 37)**2
S = S.reshape(6, 6)

S_mean = S.mean()
above_mean = S[S > S_mean]

print("S:")
print(S)
print("\nS_mean:", S_mean)

print("\nabove_mean:")
print(above_mean)

print("\nNumber of selected elements:", above_mean.size)

np.save("above_mean.npy", above_mean)
```

---

## Requirements

- Python 3
- NumPy (`pip install numpy`)

## How to Run

1. Open `ADPROG_PA2.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
2. Run all cells in order (Parts A → B → C).
3. Generated `.npy` files (`X_normalized.npy`, `div_by_4.npy`, `above_mean.npy`) will be saved in the working directory.

---

To view the program for PA2: download [ECE2112_PA1](https://github.com/jameskimezekiel-cloud/ECE2112_PA2/new/main?filename=README.md), open on Jupyter Notebook, and run all cells.

## README file Version History
- September 3, 2026 - Initial README Content 
- September 4, 2026 - Included PA2 Program to the README file
