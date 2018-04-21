**Routine Name:**           RK4_aut

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will aproximate the solution of a parabolic system of ODE's of the form y'(u)=y(u,t) y(t0)=n via a Runge-Kutta 4 Method

**Input:** A function (func), a step size (dt), an initial condition (u), left and right endpoint of the interval (a,b).

**Output:** A list containing the aproximate solution of the ODE. 

**Implementation/Code:** The following is the code for RK4_aut()

      def RK4_aut(func, dt, u, a, b):

          n=int((b-a)/dt+1)

          solu=[0]*n    

          solu[0]=u

          for i in range(1,n):

              Y1 = solu[i-1]

              Y2 = solu[i-1] + 0.5*dt*func(Y1)

              Y3 = solu[i-1] + 0.5*dt*func(Y2)

              Y4 = solu[i-1] + dt*func(Y3)

              solu[i] = solu[i-1] + dt/6*(func(Y1) + 2*func(Y2) + 2*func(Y3) +func(Y4))

          return(solu)

**Last Modified:** April/2018
