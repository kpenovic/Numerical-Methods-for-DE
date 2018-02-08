**Routine Name:**           jacobi

**Author:** Kegan Penovich

**Language:** Python


**Description/Purpose:** This routine will compute the solution to a matrix equation via Jacobi Itteration.

**Input:** There are four imputs to this function. A matrix (A), an equals to vector, and initial guess, and the number of itterations (n).

**Output:** This routine returns a vector with the solutions of the matrix equation.

**Usage/Example:**

      A=[[-2,1,0],[1,-2,1],[0,1,-2]];
      
      d=[-1,0,-1];
      
      x=[0,0,0];
      
      n=25;
      
      jacobi(A, d, x, n)

The output of this is:

      [1.0, 1.0, 1.0]

**Implementation/Code:** The following is the code for jacobi()

    def jacobi(A, d, x, n):
    
    # A: Matrix
    # d: equals to matrix
    # x: intial guess
    # n: number of itterations
    
    l=len(x);
    
    bnew=x;
    
    for k in range(n):
        b=bnew;
        
        for i in range(l):
            a=0;
            for j in range(l):
                if (i!=j):
                    a=a+A[i][j]*b[j]
            
            bnew[i]=1/A[i][i]*(d[i]-a)
    
    return(bnew)

**Last Modified:** Febuary/2018
