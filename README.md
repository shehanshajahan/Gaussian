# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import sys and numpy modules
2. Take the order of the matrix as first input
3. Create the matrix with values as user input
4. Do the elimination
5. Print X0, X1 and X2 values

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Shehan Shajahan
RegisterNumber: 23008724
*/
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
        
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end= ' ')
```

## Output:
![Screenshot 2023-12-31 202253](https://github.com/shehanshajahan/Gaussian/assets/139317389/a15f5175-e90c-4a9d-89bc-e8a24eb5473d)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

