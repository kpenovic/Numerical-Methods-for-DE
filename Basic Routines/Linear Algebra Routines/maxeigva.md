**Routine Name:**           maxeigva

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine finds the maximum eigen value of a matrix via the power method.

**Input:** A matrix, an initial vector (v), a tollerance level (tol), and a maximum number of itterations (maxiter).

**Output:** A single float value.

**Usage/Example:**

To implement the function we need only create a matrix. We will use a 4x4 Hilbert matrix

    import numpy as np
    
    A=[[1.0, 0.5, 0.3333333333333333, 0.25],
     [0.5, 0.3333333333333333, 0.25, 0.2],
     [0.3333333333333333, 0.25, 0.2, 0.16666666666666666],
     [0.25, 0.2, 0.16666666666666666, 0.14285714285714285]]
     
    v=[1,1,1]
    
    tol=.00001
    
    maxiter=10000
     
    maxeigva(A,v,tol,maxiter)
    
The output of this would be:

    1.5002142762063364

**Implementation/Code:** The following is the code for t2elip_int()

    def maxeigva(A,v,tol,maxiter):
    
    err=tol*5;
    
    lambmax=0.0
    
    itter=0
    
    while((err>tol)&(itter<maxiter)):
        
        itter+=1;
        
        y=np.matmul(A,v);
        
        u=y/v2norm(y);
        
        ut=np.transpose(u);
        
        lamb=np.matmul(ut,y) ;
        
        err=np.abs(lamb-lambmax);
        
        lambmax=lamb
        
        v=u
        
    return(lambmax)

**Last Modified:** Febuary/2018
