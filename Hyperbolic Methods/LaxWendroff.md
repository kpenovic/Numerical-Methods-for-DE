**Routine Name:**           laxWendroff

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will aproximate the solution to the advection equation via the Lax-Wendroff method.

**Input:** A initial condition (func1), Advection constant (k), time domain (a,b), spacial domain (c,d), time step (dt), spacial step (dx).

**Output:** A matrix containing the approximate solution. 

**Implementation/Code:** The following is the code for laxWendroff()

      def laxWendroff(func1, k, a, b, c, d, dt, dx):

          n = int((b-a)/dt+1)
          m = int((d-c)/dx+3)

          # Set up solution matrix

          c1 = k*dt/(2*dx)
          c2 = k*k*dt*dt/(2*dx*dx)

          solu=[]
          C=[]

          for i in range(n):
              for j in range(m):
                  C.append(0.0);
              solu.append(C);    
              C=[];

          for i in range(1,m-1):
              solu[n-1][i] = func1(dx*(i-1))

          for i in range(1,n):
              solu[n-i-1][0] = solu[n-i][1] - c1*(solu[n-i][2]-solu[n-i][0]) + c2*(solu[n-i][0] - 2*solu[n-i][1] + solu[n-i][2])
              for j in range(1,m-3):
                  solu[n-i-1][j] = solu[n-i][j] - c1*(solu[n-i][j+1]-solu[n-i][j-1]) + c2*(solu[n-i][j-1] - 2*solu[n-i][j-1] + solu[n-i][j+1])                 
              solu[n-i-1][-1] = solu[n-i][-2] - c1*(solu[n-i][-3]-solu[n-i][-1]) + c2*(solu[n-i][-1] - 2*solu[n-i][-2] + solu[n-i][-3])
          return(solu)

**Last Modified:** April/2018
