**Routine Name:**           gauss_Sidel

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will compute the solution to Ax=b via Gauss-Sidel itterative method.

**Input:** A matrix (A), a resultant vector (d), an initial guess (x), a maximum number of iterations (n), and an error tolerance level (err)

**Output:** a single vector containing an aproximate solution of x.

**Usage/Example:**

The routine needs a matrix, a resultant vector, and initial guess, maximum itterations number, and a tollerance level

We will use this to solve:

      |-2,1,0||x1| |-1| 
      |1,-2,1||x2|=| 0|
      |0,1,-2||x3| |-1|
      
      A=[[-2,1,0],[1,-2,1],[0,1,-2]]
      d=[-1,0-1]
      x=[.35,.35,.35]
      maxiter=100
      tol=.001
      
      c=gauss_Sidel(A, d, x, maxiter, tol)

Output from the lines above:

      print(c)
      
      [0.994140625, 0.994140625, 0.9970703125]

The actuall solution is [1,1,1], so we can see that it is converging to that.

**Implementation/Code:** The following is the code for gauss_Sidel()

      def gauss_Sidel(A, d, x, n, err):
          k=0

          l=len(A)

          bprev=vcopy(x)
          bnew=vcopy(x)

          for k in range(n):

              for i in range(l):
                  a=0
                  for j in range(0,i):
                      a=a+A[i][j]*bnew[j]

                  for j in range(i+1,l):
                      a=a+A[i][j]*bprev[j]

                  bnew[i]=(d[i]-a)/A[i][i] 

              e=diff(bprev,bnew)

              if(v2norm(e)<err):
                  return(bnew)

              bprev=vcopy(bnew)

          return(bnew)

**Last Modified:** March/2018
