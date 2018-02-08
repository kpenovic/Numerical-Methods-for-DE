**Routine Name:**           triDiLU

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine will compute the solution to a tridiagonal matrix equation.

**Input:** This function takes four auguments. Three vectors corresponding to the main (b), upper (c), and lower (a) diagonals of the 
matrix and a vector (d) corresponding to the resultant vector.

**Output:** This routine returns a vector with the solutions of the matrix equation.

**Usage/Example:**

Suppose we have a matrix equation of the form: Ax=y, and A is a tridiagonal matrix. To solve this equation we do the following:

        |-2 1 0|   |-1|
      A=|1 -2 1| d=| 0|
        |0 1 -2|   |-1|
        
      b=[-2,-2,-2]
      a=[1,1]
      c=[1,1]
      d=[-1,0,-1]
      
      triDiLU(b, a, c, d)

Output from the lines above:

      [1, 1, .9999999999999]

This is the x vector from our equation. 

**Implementation/Code:** The following is the code for triDiLU()

    def triDiLU(b, a, c, x):
    n=len(x);
    
    #b Diagonal
    #a Lower Diagonal
    #c Upper Diagonal
    
    #x Equals to vector
    
    v=[0]*n # temporary for the LU factorazation
    l=[0]*n # temporary for the LU factorazation
    
    y=[0]*n # temp for solving the matrix equation
    u=[0]*n # temp for solving the matrix equation
    
    v[0]=b[0];
    
    for i in range(1, n):
        l[i]=a[i-1]/v[i-1];
        v[i]=b[i]-l[i]*c[i-1];
    
    y[0]=x[0];
    
    for i in range(1, n):
        y[i]=x[i]-l[i]*y[i-1];
        
    u[n-1]=y[n-1]/v[n-1];
    
    for i in range((n-2),-1,-1):
        u[i]=(y[i]-c[i]*u[i+1])/v[i];
        
    return(u)   
    
**Last Modified:** Febuary/2018
