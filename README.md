# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
1.Input matrix dimensions and initialize augmented matrix and solution vector.
2.Populate the augmented matrix with user inputs.
3.Perform Gaussian elimination to reduce the matrix to upper triangular form, ensuring no division by zero. 
4.Back substitute to compute solution values for the variables.
5.Print the solution vector formatted to two decimal places.
```
## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: SANTHOSHKUMAR.J
RegisterNumber: 25016468 
'''
import sys
import numpy as np
data=list(map(float,sys.stdin.read().split()))
n=int(data[0])
vals=data[1:]
A=np.array(vals, dtype=float).reshape(n,n+1)
for k in range(n-1):
    for i in range(k+1,n):
        factor = A[i,k]/A[k,k]
        A[i,k:]-=factor * A[k,k:]
x=np.zeros(n)
for i in range(n-1,-1,-1):
    x[i]=(A[i,-1] - np.dot(A[i,i+1:n],x[i+1:n]))/A[i,i]
parts=[f"X{i} = {x[i]:.2f}" for i in range(n)]
print(" ".join(parts))
```

## Output:
![gaussian elimination]()
<img width="710" height="374" alt="Screenshot 2025-11-27 111513" src="https://github.com/user-attachments/assets/ddcf0296-986c-44d9-b8ba-1cb143f31ad3" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

