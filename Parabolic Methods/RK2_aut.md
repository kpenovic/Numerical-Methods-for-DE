**Routine Name:**           RK2_aut

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will aproximate the solution of a parabolic system of ODE's of the form y'(u)=y(u,t) y(t0)=n via a Runge-Kutta 2 Method

**Input:** A function (func), a step size (delt), an initial condition (u), left and right endpoint of the interval (a,b), and the number of ODE's (m).

**Output:** A list containing the aproximate solution of the ODE. 

**Implementation/Code:** The following is the code for RK2_aut()

      def RK2_aut(func, delt, u, a, b):

          n=int((b-a)/delt+1)

          solu=[0]*n    

          solu[0]=u

          for i in range(1,n):

              ustar = solu[i-1] + 0.5*dt*func(solu[i-1])

              solu[i] = solu[i-1] + dt*func(ustar)

          return(solu)

**Last Modified:** April/2018
