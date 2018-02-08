**Routine Name:**           thomas

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
      
      thomas(b, a, c, d)

Output from the lines above:

      [1, 1, .9999999999999]

This is the x vector from our equation. 

**Implementation/Code:** The following is the code for smaceps()

      def thomas(b, a, c, d):
    
      #b Diagonal
      #a Lower Diagonal
      #c Upper Diagonal
    
      #d Equals to vector
    
      n=len(d);
    
      x=[0]*n;    

      for i in range(1,n):
        b[i]=b[i]-c[i-1]*a[i-1]/b[i-1];
        d[i]=d[i]-d[i-1]*a[i-1]/b[i-1];
    
      x[n-1]=d[n-1]/b[n-1];
    
      for i in range((n-2),-1,-1):
        x[i]=(d[i]-x[i+1]*c[i])/b[i];
        
      return(x)
      
**Last Modified:** Febuary/2018
