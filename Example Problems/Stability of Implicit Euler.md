**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This is code for showing the issues that can arrise with the time step in the Implicit Euler Method for various problems.

**Example:**

      # Problem 1
      
      # These are the function f(u,t) for the ODE's of the form u'=f(u,t)
      # This is also the appropriate derivitives for using the Newton-Raphson Method
      
      def func71(u,t):

          return(-np.sin(t))

      def dfunc71(u,t):

          return(0.0)

      def func72(u,t):

          return(-10.0*(u - np.cos(t)) - np.sin(t))

      def dfunc72(u,t):

          return(-10.0)

      def func73(u,t):

          return(-2100.0*(u - np.cos(t)) - np.sin(t))

      def dfunc73(u,t):

          return(-2100.0)

      # These are the different time steps we are going to look at.

      dt1 = 0.001000
      dt2 = 0.000976
      dt3 = 0.000950
      dt4 = 0.000800
      dt5 = 0.000400

      # The initial condition (u), and the solution boundry ([a,b])
      
      u=1.0
      a=0.0
      b=2.0
      
      tol = .00001
      maxiter = 1000

      # Length of the solution interval (n1, n2, n3, n4, n5), and the vectors to hold the exact values.

      n1=int((b-a)/dt1+1)

      n2=int((b-a)/dt2+1)

      n3=int((b-a)/dt3+1)

      n4=int((b-a)/dt4+1)

      n5=int((b-a)/dt5+1)

      x1=[0]*n1

      x2=[0]*n2

      x3=[0]*n3

      x4=[0]*n4

      x5=[0]*n5
      
      # We will use these to evaluate the exact solution. 

      for i in range(n1):
          x1[i]=a+i*dt1

      for i in range(n2):
          x2[i]=a+i*dt2

      for i in range(n3):
          x3[i]=a+i*dt3    

      for i in range(n4):
          x4[i]=a+i*dt4

      for i in range(n5):
          x5[i]=a+i*dt5 

      # Using Implicit Euler Method to approximate the ODE's.

      y1 = im_euler_aut(func71, dfunc71, u, dt1, a, b, tol, maxiter)

      y2 = im_euler_aut(func72, dfunc72, u, dt1, a, b, tol, maxiter)

      y3 = im_euler_aut(func73, dfunc73, u, dt1, a, b, tol, maxiter)

      y4 = im_euler_aut(func73, dfunc73, u, dt2, a, b, tol, maxiter)

      y5 = im_euler_aut(func73, dfunc73, u, dt3, a, b, tol, maxiter)

      y6 = im_euler_aut(func73, dfunc73, u, dt4, a, b, tol, maxiter)

      y7 = im_euler_aut(func73, dfunc73, u, dt5, a, b, tol, maxiter)
      
      # Error between the last elements in the approximation against the exact solution.

      e1 = abs(y1[-1]-np.cos(b))

      e2 = abs(y2[-1]-np.cos(b))

      e3 = abs(y3[-1]-np.cos(b))

      e4 = abs(y4[-1]-np.cos(b))

      e5 = abs(y5[-1]-np.cos(b))

      e6 = abs(y6[-1]-np.cos(b))

      e7 = abs(y7[-1]-np.cos(b))

      print(e1)

      print(e2)

      print(e3)

      print(e4)

      print(e5)

      print(e6)

      print(e7)

**Last Modified:** April/2018
