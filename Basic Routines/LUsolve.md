**Routine Name:**           LUsolve

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine solves Matrix equations given the matrix LU decomposition and the solution vector.

**Input:** The LU decomposition (L, U) and a solutions vector (b)

**Output:** This routine returns a vector containging the solution of the matrix equation.

**Usage/Example:**

To implement the function we would need a matrix and solutions vector:

    A=[[1,2,3],[1,3,4],[1,1,1]];
    b=[6,8,3]
    
    ret=NaiveLU(A)
    
    x=LUsolve(ret[1],ret[0],b)
    
    print(x)
    
We ould now only need to have the rest of the set up to initialize this problem.

    [1.0, 1.0, 1.0]

**Implementation/Code:** The following is the code for LUsolve()

    def LUsolve(L,U,b):
    
    n=len(b);

    x=[0]*n

    x[0]=b[0];


    for i in range(1,n):
        s=0.0;
        for j in range(i):
            #print(L[i][j])
            s+=L[i][j]*x[j]
        x[i]=b[i]-s  

    x[n-1]=x[n-1]/U[n-1][n-1]

    for i in range(n-2,-1,-1):
        s=0.0;
        for j in range(i+1,n):
            s+=U[i][j]*x[j];
        
        x[i]=(x[i]-s)/U[i][i];
        
    return(x) 

**Last Modified:** Febuary/2018
