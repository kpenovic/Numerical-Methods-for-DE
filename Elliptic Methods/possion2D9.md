**Routine Name:**           possion2D9

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine initializes the matricies and vector needed to solve a poisson problem using a 9 point stencil. 

**Input:** The mesh size (mesh), the function the laplacian is set equal to (func), the size of the square over which we are looking at (size), and the point that forms the corner of the square (a,b).

**Output:** This routine returns a matrix (B), and a vector (A).

**Usage/Example:**

To implement the function we need a mesh size, a function, a size for the square, and the bottom left corner point.

    import numpy as np
    
    def func(x,y):
        return(np.sin(x*y))
    
    mesh=10
    size=1
    a=0
    b=0
    
    ret=possion2D9(mesh, func, size, a, b)    
    
ret now holds a 100x100 matrix, a 100 element vector. The finite difference solution could then be solved for using a matrix equation solver of your choice.    

**Implementation/Code:** The following is the code for possion2D9()

     def possion2D9(mesh, func, size, a, b):

      B=[] # This will hold the matrix
      C=[] # dummy variable

      h=size/mesh # step size

      n=mesh*mesh; # matrix size (n by n)

      A=[0]*n # solution vector                     

      for i in range(n):         # initialize the matrix
          for j in range(n):
              C.append(0);
          B.append(C);    
          C=[];

      for i in range(n-1):
          B[i][i]=-20

          if(((i+1)%mesh)!=0): # keeps ones out of the identity block diagonals
              B[i+1][i]=4
              B[i][i+1]=4

      for i in range(mesh*(mesh-1)-1): # Fills in the Identity sub and super block diagonals
          B[mesh+i][i]=4
          B[i][mesh+i]=4

          if(((i+1)%mesh)!=0): # keeps ones out of the main diagonal
              B[mesh+i+1][i]=1
              B[mesh+i][i+1]=1
              B[i+1][mesh+i]=1
              B[i][mesh+i+1]=1

      B[n-mesh-1][n-1]=4
      B[n-1][n-mesh-1]=4
      B[n-1][n-1]=-20 # Pick up the last diagonal entry that was skipped in the above loop

      i=0;
      j=1; # We are never evaluating the function on the boundary, we will always be at least h away from the boundary
      k=1; # We are never evaluating the function on the boundary

      while(i<n):

          if(i%mesh==0): # Each time you complete a pass, move up one and reset the x value
              j=1;       # We are never evaluating the function on the boundary
              k+=h
          A[i]=func((a+h*j),(b+h*k));

          j+=1
          i+=1

      return(B,A) 
   
**Last Modified:** Febuary/2018
