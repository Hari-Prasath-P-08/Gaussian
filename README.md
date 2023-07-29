# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import numpy as np.
2. Get the size of the matrix from user and create empty matrix and vector.
3. using for loop get elements for matrix and vector.
4. Use another for loop to take each element in the matrix.
5. Solve row echelon form.
6. Perform back substitution.
7. Print the value in two decimal points.
8. End the program.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Hari Prasath. P
RegisterNumber: 23005079
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
        
for i in range(n):
    if a[i][i]==0:
        sys.exit("Divide by zero detected")
        
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
    print('X%d = %0.2f'%(i,x[i]),end=" ")
    
```

## Output:
![output](/Screenshot%202023-07-29%20135915.png)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.
