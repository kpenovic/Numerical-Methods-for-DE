**Routine Name:**           ODE43_aut

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will aproximate the solution of an of ODE of the form y'(u)=y(u,t) y(t0)=n via a Predictor-Corrector method. The Preditction step is a fouth order Adams-Bashford method while the correction is a third order Adams-Moulton method.

**Input:** A function (func), a step size (dt), an initial condition (u), left and right endpoint of the interval (a,b).

**Output:** A list containing the aproximate solution of the ODE. 

**Implementation/Code:** The following is the code for ODE43_aut()

      def ODE43_aut(func, dt, u, a, b):

          n=int((b-a)/dt+1)

          solu=[0]*n    

          solu[0]=u

          for i in range(1, 4):

              solu[i]=solu[i-1]+dt*func(solu[i-1])

          for i in range(4, n):

              f1 = func(solu[i-1])
              f2 = func(solu[i-2])
              f3 = func(solu[i-3])

              solu[i] = solu[i-1] + dt/24*(-9*func(solu[i-4]) + 37*f3 - 59*f2 + 55*f1)

              solu[i] = solu[i-1] + dt/24*(f3 - 5*f2 + 19*f1 + 9*func(solu[i]))

          return(solu)

**Last Modified:** April/2018
