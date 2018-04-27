**Routine Name:**           upwinding

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will aproximate the solution to the advection equation via the Upwinding method.

**Input:** A initial condition (func1), Advection constant (k), time domain (a,b), spacial domain (c,d), time step (dt), spacial step (dx).

**Output:** A matrix containing the approximate solution. 

**Implementation/Code:** The following is the code for upwinding()

      def upwinding(func1, k, a, b, c, d, dt, dx):

          n = int((b-a)/dt+1)
          m = int((d-c)/dx+2)

          # Set up solution matrix

          solu=[]
          C=[]

          for i in range(n):
              for j in range(m):
                  C.append(0.0);
              solu.append(C);    
              C=[];


          if(k<0):

              for i in range(1,m):
                  solu[n-1][i] = func1(dx*(i-1))

              for i in range(1,n):
                  for j in range(1,m):
                      solu[n-i-1][j] = solu[n-i][j]-k*dt/(dx)*(solu[n-i][j-1]-solu[n-i][j])

          else:

              for i in range(0,m-1):
                  solu[n-1][i] = func1(dx*(i-1))

              for i in range(1,n):
                  for j in range(m-1):
                      solu[n-i-1][j] = solu[n-i][j]-k*dt/(dx)*(solu[n-i][j]-solu[n-i][j+1])

          return(solu) 

**Last Modified:** April/2018
