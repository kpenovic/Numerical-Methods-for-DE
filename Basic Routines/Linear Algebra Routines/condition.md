**Routine Name:**           condition

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine computes the condition number for a matrix.

**Input:** A matrix (A) and a tollerance (tol)

**Output:** This routine returns a single float value.

**Usage/Example:**

To implement the function we need a Matrix and a tollerance level:

    A=[]
    C=[]
    
    k=5

    for i in range(k):
        for j in range(k):
            C.append(0);
        A.append(C);
        C=[];


    for j in range(k-1):
        A[j][j]=2
        A[j+1][j]=-1
        A[j][j+1]=-1

    A[k-1][k-1]=-2
    
    tol=.0001
    
    condition(A,tol)
    
The output of the code is:

    8.5206721383014443

**Implementation/Code:** The following is the code for condition()

    def condition(A,tol):
    
        n=len(A);

        v=[1]*n;

        maxiter=1000;

        a=maxeigva(A, v, tol, maxiter);

        b=mineigva(A, v, tol, maxiter);

    return(a*b)
    

**Last Modified:** Febuary/2018
