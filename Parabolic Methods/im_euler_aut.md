**Routine Name:**           im_euler_aut

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will aproximate the solution of an autonomous ODE's of the form y'(u)=y(u) y(t0)=n using an Implicit Euler Method

**Input:** A function (func), derivitive of that function (dfunc) a step size (delt), an initial condition (u), left and right endpoint of the interval (a,b), tolerance for N-R method (tol), maximum number of itteration for N-R method (maxiter).

**Output:** A list containing the aproximate solution of the ODE's. 

**Implementation/Code:** The following is the code for im_euler_aut()

      def im_euler_aut(func, dfunc, u, dt, a, b, tol, maxiter):

          n=int((b-a)/dt+1)

          solu=[0]*n    

          solu[0]=u

          for i in range(1,n):

              k=0
              err=5*tol
              old=1.2 # usinversal staring point for the N-R method

              while((err>tol)&(k<maxiter)): # Newton-Raphson Methed 

                  new = old-(old-solu[i-1]-dt*func(old))/(1-dt*dfunc(old))

                  err=abs(new-old)

                  old=new

              solu[i]=old

          return(solu)

**Last Modified:** April/2018
