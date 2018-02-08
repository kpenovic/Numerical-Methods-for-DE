**Routine Name:**           fdcoeff

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine will compute the coefficients for a given finite difference method.

fdcoeff(k,xbar,x)

**Input:** There are three inputs for this function. An order term (k) a center (xbar) and a vector of stencil points (x).

**Output:** A vector containing the coefficients for the given finite difference method.

**Implementation/Code:** The following is the code for fdcoeff()

    def fdcoeff(k,xbar,x):
    n=len(x);
    A=[]
    B=[]
    b=[]
    
    for i in range(n):
        for j in range(n):
            B.append(1);
        A.append(B);    
        B=[];
    
    xrow=[];
    for i in range(n):
        xrow.append(x[i]-xbar);
        
    for i in range(2,n):
        for j in range(n):
            A[i][j]=(xrow[j]^(i-1)/fact(i-1))
            
    for i in range(n):
        b.append(0);
        
    b[k+1]=1;
    
    c=gauss(A, b)
    
    return(c)
     
**Last Modified:** Febuary/2018
