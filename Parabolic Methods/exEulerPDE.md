**Routine Name:**           exEulerPDE

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine will aproximate the solution of a PDE of the form: du/dt=k*d2u/dx2

**Input:** An initial condition (func1), a left boundary condition (func2), a right boundary condition (func3), a diffusion constant (k), a time step (dt), a spacial step (dx), the time domain over which we are approximating (a,b), and the spacial domain over which we are solving (c,d). 

**Output:** A matrix containing the aproximate solution (it will be a ((b-a)/dt+1)X((b-a)/dx+1)) 

**Implementation/Code:** The following is the code for exEulerPDE()

      def exEulerPDE(func1, func2, func3, k, dt, dx, a, b, c, d):

          # func1: Initial Condition
          # func2: Left Boundary Condition
          # func3: Right Boundary Condition
          # k: heat coefficient
          # dt: Time Step
          # dx: Spatial Step
          # (a,b): Time Domain
          # (c,d): Spatial Domain

          if(dt/(dx*dx)>=0.5):
              return("dt/(dx^2)>=0.5, Adjust time step")

          n = int((b-a)/dt+1)
          m = int((d-c)/dx+1)

          # Set up solution matrix

          solu=[]
          C=[]

          for i in range(n):
              for j in range(m):
                  C.append(0.0);
              solu.append(C);    
              C=[];

          # Set up initial conditions and boundary conditions

          for i in range(m):
              solu[n-1][i] = func1(dx*i)    

          for i in range(n):
              solu[m-i-1][0] = func2(dt*i)
              solu[m-i-1][(m-1)] = func3(dt*i)

          # The Explicit euler algorithm

          for i in range(1,n):
              for j in range(1,m-1):
                  solu[n-i-1][j] = solu[n-i][j]+dt/(dx*dx)*(solu[n-i][j-1]-2*solu[n-i][j]+solu[n-i][j+1])

          return(solu) 

**Last Modified:** April/2018
