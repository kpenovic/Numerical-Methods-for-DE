**Routine Name:**           Demonstrating how to use the program beamWarming() to solve the advection equation.

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will demonstrate the use of beamWarming() to solve the PDE u_t + a*u_x = 0.


**Usage/Example:**

We will first need to define a function that serves as our initial condition. We will use a step function as it is a easy to see what the solution is doing, and highlights the issues that arrise in using this method. 

      def func1(x):
          if(x>=.5):
              return(0.0)
          else:
              return(1.0)

We will now need to define the window over which we are solving, and appropriate time and spacial steps.  

      a=0
      b=1
      c=0
      d=1

      dt=.001
      dx=.01

      k=-0.9

      solu = beamWarming(func1, k, a, b, c, d, dt, dx)
      
solu now holds a matrix containing the solutions for each of the time steps. This is an ineficient use of memory, but it did make it easier to watch the solution evolve. Eventually this could be fixed. We can now plot the solution at different time steps and watch the solution evolve.

      m = int((d-c)/dx+2)

      x=[0]*m

      for i in range(1,m-2):
          x[i] = dt*(i-1)

      plt.scatter(x, solu[-1], c="b", marker="+")
      plt.scatter(x, solu[-200], c="r", marker="+")
      plt.scatter(x, solu[-400], c="g", marker="+")
      plt.scatter(x, solu[-600], c="c", marker="+")
      plt.show()

**Last Modified:** April/2018
