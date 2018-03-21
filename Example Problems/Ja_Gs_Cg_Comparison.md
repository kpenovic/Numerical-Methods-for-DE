**Routine Name:**           Comparing the itterations till convergence for Jacobi, Gauss-Sidel, and Conjugate Gradiant Method

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will demonstrate the speed of these three methods comparative to eachother.

**Usage/Example:**

To do this we will generate maticies of different sizes to have each method solve. To do this we will use possion2D5 to generate these matricies and vectors to test them on.
This matrix is the one that results from a finite difference method applied to a 2D Poisson PDE. The code will record the number of itterations it takes to solve the given maxtrix.
One thing to note is that n in this case will be the mesh size, so the coresponding matrix will be of size n^2. 

      n=20 

      gs=[0]*n
      ja=[0]*n
      cg=[0]*n

      y=[0]*n

      for i in range(3,n+3):

          mesh=i
          size=1
          a=0
          b=0

          B,A=possion2D5(mesh, func, size, a, b)

          x=[0]*mesh*mesh

          n=1000;

          err=.01

          gs[i-3]=gauss_Sidel(B, A, x, n, err)

          x=[0]*mesh*mesh

          ja[i-3]=jacobi(B, A, x, n, err)

          x=[0]*mesh*mesh

          cg[i-3]=congrad(B, A, x, n, err)
          
      for i in range(n):
        print("Matrix Size =",(i+3)*(i+3),"| gs: ", gs[i], "| ja: ", ja[i], "| cg: ", cg[i])

The results of this are:

      Matrix Size = 9 | gs:  7 | ja:  10 | cg:  4
      Matrix Size = 16 | gs:  10 | ja:  15 | cg:  5
      Matrix Size = 25 | gs:  14 | ja:  22 | cg:  6
      Matrix Size = 36 | gs:  19 | ja:  30 | cg:  7
      Matrix Size = 49 | gs:  25 | ja:  38 | cg:  9
      Matrix Size = 64 | gs:  31 | ja:  48 | cg:  10
      Matrix Size = 81 | gs:  38 | ja:  59 | cg:  11
      Matrix Size = 100 | gs:  45 | ja:  71 | cg:  13
      Matrix Size = 121 | gs:  53 | ja:  84 | cg:  14
      Matrix Size = 144 | gs:  62 | ja:  99 | cg:  15
      Matrix Size = 169 | gs:  72 | ja:  114 | cg:  17
      Matrix Size = 196 | gs:  82 | ja:  131 | cg:  18
      Matrix Size = 225 | gs:  93 | ja:  148 | cg:  19
      Matrix Size = 256 | gs:  105 | ja:  167 | cg:  20
      Matrix Size = 289 | gs:  118 | ja:  187 | cg:  22
      Matrix Size = 324 | gs:  131 | ja:  207 | cg:  23
      Matrix Size = 361 | gs:  144 | ja:  229 | cg:  24
      Matrix Size = 400 | gs:  159 | ja:  253 | cg:  26
      Matrix Size = 441 | gs:  174 | ja:  277 | cg:  27
      Matrix Size = 484 | gs:  190 | ja:  302 | cg:  28

**Last Modified:** March/2018
