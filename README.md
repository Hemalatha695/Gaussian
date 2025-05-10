# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
## step1:
Input the Augmented Matrix
Read the number of unknowns n.
Create a (n x n+1) matrix a to store coefficients and constants.
Use nested loops to input each element of the augmented matrix.
## step 2:
Forward Elimination to Convert to Upper Triangular Form
For each pivot row i:
Check for division by zero at the diagonal element a[i][i].
For each row j below i, compute the ratio a[j][i] / a[i][i] and eliminate the unknown by updating row j.
## step3:
Back Substitution to Find Solution
Start with the last variable x[n-1] = a[n-1][n] / a[n-1][n-1].
Move upward through the matrix:
For each variable x[i], subtract the known values from the RHS, then divide by a[i][i].
## step4:
Store each solution in the array x.
## step5:
Loop through the solution array and print each variable x[i] formatted to two decimal places.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:Hemalatha A 
RegisterNumber: 212224240056
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
        sys.exit('Divide by zero detector!')
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
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
![alt text](<maths exp 6.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

