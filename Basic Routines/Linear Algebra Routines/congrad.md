**Routine Name:**           congrad

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will compute the solution to Ax=b via the Conjugate-Gradiant method.

**Input:** A matrix (A), a resultant vector (f), an initial guess (u), maximum number of itterations (n), a tollerance level (err)

**Output:** A vector containing an aproximate solution of x. 

**Usage/Example:**

The routine needs a matrix, a resultant vector, and initial guess, maximum itterations number, and a tollerance level

We will use this to solve: 

      |-2,1,0||x1| |-1| 
      |1,-2,1||x2|=| 0| 
      |0,1,-2||x3| |-1|
      
      A=[[-2,1,0],[1,-2,1],[0,1,-2]]
      f=[-1,0-1]
      u=[.35,.35,.35]
      maxiter=100
      tol=.001
      
      c=congrad(A, f, u, maxitter , tol)

Output from the lines above:

      print(c)
      
      [1.0, 1.0, 1.0]

**Implementation/Code:** The following is the code for congrad()

      def congrad(A, f, u, n, err):

          l=len(A)

          uprev=vcopy(u)

          rprev=diff(f,vmmult(A,u))

          pprev=vcopy(rprev)

          count=0

          for i in range(n):

              w=vmmult(A,pprev)

              count+=l*l

              a=dot(rprev,rprev)/dot(pprev,w)

              count+=2*l+1

              unew=diff(uprev,scamult(-a,pprev))

              count+=2*l

              rnew=diff(rprev,scamult(a,w))

              count+=2*l

              if(v2norm(rnew)<err):

                  return(unew)

              b=dot(rnew,rnew)/dot(rprev,rprev)

              count+=2*l+1

              pprev=(diff(rnew,scamult(-b,pprev)))

              count+=2*l

              rprev=rnew

              uprev=unew

          return(unew)

**Last Modified:** March/2018
