# LU Decomposition 

## AIM:
To write a program to find the LU Decomposition of a matrix.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
question 1

1.Import the python numpy libray ,Take input for matrix and right hand side vector 2.Decompose the matrix using lu factorization
2.solve for the unknow vector usig the lu decomposition
3.using the lu()and pass the variable when the variable value in array
4.And print the upper and lower matrix
question 1

1.Import the python numpy libray ,Take input for matrix and right hand side vector 2.Decompose the matrix using lu factorization
2.solve for the unknow vector usig the lu decomposition
3.using the linalg_solve() and linalg_factor() pass the variable when the variable value in array
4.And print the final answer

## Program:
(i) To find the L and U matrix

/*
Program to find the L and U matrix.
Developed by:Mohamed Muzammil T 
RegisterNumber:25018338 
*/
import numpy as np
from scipy.linalg import lu
a=eval(input())
b=np.array(a)
p,l,u=lu(b)

print(l)
print(u)

(ii) To find the LU Decomposition of a matrix

/*
Program to find the LU Decomposition of a matrix.
Developed by:Mohamed Muzammil T
RegisterNumber:25018338 
*/
import numpy as np

def solve_lu(A, b):
    A = np.array(A, dtype=float)
    b = np.array(b, dtype=float)
    n = len(A)

    L = np.eye(n)
    U = A.copy()

    for i in range(n):
        for j in range(i + 1, n):
            factor = U[j, i] / U[i, i]
            L[j, i] = factor
            U[j, i:] -= factor * U[i, i:]

    y = np.zeros(n)
    for i in range(n):
        y[i] = b[i] - np.dot(L[i, :i], y[:i])

    x = np.zeros(n)
    for i in range(n - 1, -1, -1):
        x[i] = (y[i] - np.dot(U[i, i+1:], x[i+1:])) / U[i, i]
    print(x)
A=eval(input())
b=eval(input())
solve_lu(A,b)

## Output:
![lu decomposition]()
<img width="1903" height="993" alt="Screenshot 2025-12-24 210708" src="https://github.com/user-attachments/assets/6421673a-e3c1-4ca0-94d6-43933a4ff74e" />
<img width="1897" height="923" alt="Screenshot 2025-12-24 210725" src="https://github.com/user-attachments/assets/56b5fb00-2f3a-40d9-ae76-0d5c03933aa4" />




## Result:
Thus the program to find the LU Decomposition of a matrix is written and verified using python programming.

