**Routine Name:**           NaiveLU

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine decomposses a matrix into its LU factorization. This is a Naive implementation, that is without any pivoting. This works well if the matrix already has the largest elements on the diagonal.

**Input:** A square matrix (A)

**Output:** Two matricies contatining the L and U factorization of A.

**Usage/Example:**

To implement the function we need a matrix:

    B=[[1,2,3],[1,3,4],[1,1,1]]

    ret=NaiveLU(B)

    pprint(ret[0])
    pprint(ret[1])
    
The output is:

    1.0	  0	    0	 
    1.0	 1.0	  0	 
    1.0	-1.0	-2.0	 

    1.0	2.0	  3.0	 
    0	  1.0	  1.0	 
    0	   0	 -1.0	

**Implementation/Code:** The following is the code for NaiveLU()

    def NaiveLU(A):
    n = len(B)

    L=[]
    U=[]
    C=[]

    for i in range(n):
        for j in range(n):
            C.append(0);
        L.append(C);
        C=[];

    for i in range(n):
        for j in range(n):
            C.append(0);
        U.append(C);
        C=[];

    for j in range(n):
        L[j][j]=1
        for i in range(j+1):
            s1=0.0;
            for k in range(i):
                s1+=U[k][j]*L[i][k]
            U[i][j]=B[i][j]-s1

        for i in range(j,n):
            s2=0.0;
            for k in range(j):
                s2=U[k][j]*L[i][k]
            L[i][j]=(B[i][j]-s2)/U[j][j]
            
    return(L,U)

**Last Modified:** Febuary/2018
