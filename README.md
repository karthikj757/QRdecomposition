# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
import numpy as np

def qr_decomposition(A):
    A = np.array(A,dtype=float)
    m,n=A.shape
    
    Q=np.zeros((m,n))
    R=np.zeros((n,n))
    
    for j in range(n):
        v=A[:,j]
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
  
  
A=np.array(eval(input())) 

Q,R=qr_decomposition(A) 

print("The Q Matrix is \n",Q)
print("The R Matrix is \n",R)

```

## Output

<img width="1231" height="382" alt="Screenshot 2026-02-07 093208" src="https://github.com/user-attachments/assets/09d99bdb-31c8-4bcf-8a4b-01cace473258" />
<img width="1262" height="626" alt="Screenshot 2026-02-07 093235" src="https://github.com/user-attachments/assets/37f183fd-13ef-42c0-a016-d9ffffcb4bb2" />
<img width="1262" height="594" alt="Screenshot 2026-02-07 093250" src="https://github.com/user-attachments/assets/23a3a079-edf0-4143-97db-bb9fc3d86675" />

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
