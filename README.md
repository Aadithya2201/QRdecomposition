# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

  ![WhatsApp Image 2023-12-27 at 15 07 48_a54f3207](https://github.com/Aadithya2201/QRdecomposition/assets/145917810/446dc9a4-f5b3-4dfc-b822-511d7f39234a)



3.	Obtain the Q matrix   
    ![WhatsApp Image 2023-12-27 at 15 08 23_11855b3d](https://github.com/Aadithya2201/QRdecomposition/assets/145917810/491a170b-d91e-4c53-9af7-e803034904b0)

4.	Construct the upper triangular matrix R
    ![WhatsApp Image 2023-12-27 at 15 08 50_e7a8c75a](https://github.com/Aadithya2201/QRdecomposition/assets/145917810/7c6d53ad-0827-4878-8b10-7cd8ee0b093b)




## Program:
### Gram-Schmidt Method

```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Aadithya.R
RegisterNumber: 23006361
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
a=np.array(eval(input()))
QR_Decomposition(a)

```

## Output
![Screenshot 2023-12-27 145602](https://github.com/Aadithya2201/QRdecomposition/assets/145917810/5440134e-5f99-4cf0-957a-6f033b8ab8ed)
![Screenshot 2023-12-27 145634](https://github.com/Aadithya2201/QRdecomposition/assets/145917810/f31c011a-f21c-4dd8-8f2f-3e9577a716c3)
![Screenshot 2023-12-27 145653](https://github.com/Aadithya2201/QRdecomposition/assets/145917810/cf8a358d-4a3c-463f-98d7-184e1deeb0e6)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
