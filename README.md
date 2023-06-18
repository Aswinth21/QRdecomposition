# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![image](https://github.com/Aswinth21/QRdecomposition/assets/120236638/454151c4-3882-4680-902b-d146931c51c6)


    ![image](https://github.com/Aswinth21/QRdecomposition/assets/120236638/5edf467b-1c0e-4703-bcea-c007de1586a2)


    ![image](https://github.com/Aswinth21/QRdecomposition/assets/120236638/4b4c12a2-0b98-460e-b5be-00a2bf496e21)

3.	Obtain the Q matrix   
    ![image](https://github.com/Aswinth21/QRdecomposition/assets/120236638/2d27b6a0-46ee-4a81-9a80-630a32411cde)
4.	Construct the upper triangular matrix R
    ![image](https://github.com/Aswinth21/QRdecomposition/assets/120236638/9b35e8e3-beb7-4674-afae-bac26b0ae8fe)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Aswinth.T
RegisterNumber: 212222230015
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range (1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i] @ q[:,j]) *q[:,j]
        q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    r=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            r[i,j]=A[:,j] @ q[:,i]
    print(q) 
    print(r)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output
![image](https://github.com/Aswinth21/QRdecomposition/assets/120236638/8f974d6d-021e-487d-8f0d-cdc69730c23a)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
