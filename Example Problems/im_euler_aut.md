**Routine Name:**           Demonstrating how to use the program im_euler_aut() to solve first order autonomous differential equations.

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will demonstrate the use of im_euler_aut() to solve the ODE's y'=lambda*y and y'=gamma*y-beta*y^2.


**Usage/Example:**

To do this we will define the functions we are looking to solve. For y'=lambda*y we will do it as follows for lambda=1,-1,-100:

      def func1(x):

          return(x)

      def func2(x):

          return(-x)

      def func3(x):

          return(-100*x)
          
For the logistic function y'=gamma*y-beta*y^2 we will do it as follows with alpha=0.1 and beta=0.0001:

      def func4(x):

          return(.1*x-.0001*x*x)
          
We will also need the derivitives of each of these for the Newton-Raphson Method method:

      def dfunc1(x):
          return(1.0)

      def dfunc2(x):
          return(-1.0)

      def dfunc3(x):
          return(-100.0)

      def dfunc4(x):
          return(.1-.0002*x)    
    
We will also want to compare our approximate solutions to the exact solutions, so we will need the exact solutions:

      import numpy as np

      def scamult(a,b):
          n=len(b)

          c=[0]*n

          for i in range(n):
              c[i]=a*b[i]

          return(c)

      def ode_basic(x, lamb, x0):

          return(x0*np.exp(scamult(lamb,x)))

      def ode_logistic(x, gamma, beta, x0):

          K=gamma/beta

          A=(K-x0)/x0

          return(K/(1+A*np.exp(scamult(-gamma, x))))  
          
We will now get set our initial conditions and parameters and use im_euler_aut() to obtain our approximations:

      tol=.001
      maxiter=100
      u=1.0  # Initial value for the basic ode y'=lambda*y, y0=u
      a=0.0  # Left bound of the interval
      b=1.0  # Right bound of interval
      dt=.01  # Step size
      p0_1=50 # Initial value for the logistic equation
      lamb1=1.0 # varius lambda values for y'=lambda*y
      lamb2=-1.0
      lamb3=-100.0

      y1=im_euler_aut(func1, dfunc1, u, dt, a, b, tol, maxiter)

      y2=im_euler_aut(func2, dfunc2, u, dt, a, b, tol, maxiter)

      y3=im_euler_aut(func3, dfunc3, u, dt, a, b, tol, maxiter)

      y4=im_euler_aut(func4, dfunc4, p0_1, dt, a, b, tol, maxiter)
      
We would now like to plot it to see how our approximation compares to the exact solution. To do this we will do the following:

      import matplotlib.pyplot as plt

      n=int((b-a)/dt+1)

      y=[0]*n       # A vector that contains the location of your approximations. We will evaluate the exact solution at these points.

      for i in range(n):
          y[i]=a+i*dt

      plt.scatter(y, y1, c="b", marker="+")                   # plot any of your solutions. Just change the lambda_ an y_.             
      plt.scatter(y, ode_basic(y,lamb1,u), c="r", marker="+") # this will plot the solutions to y'=lambda*y
      plt.show()

      # plt.scatter(y, y4, c="b", marker="+")
      # plt.scatter(y, ode_logistic(y,0.1, 0.0001, p0_1), c="r", marker="+") # plot solutions to y'=gamma*y-beta*y^2 
      # plt.show()

**Last Modified:** April/2018
