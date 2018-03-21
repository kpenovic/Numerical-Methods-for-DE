**Routine Name:**           ex_euler

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will aproximate the solution of a parabolic system of ODE's of the form y'(u)=y(u,t) y(t0)=n

**Input:** A function (func), a step size (delt), an initial condition (u), left and right endpoint of the interval (a,b), and the number of ODE's (m).

**Output:** A 2D list containing the aproximate solution of the system of ODE's. 

**Implementation/Code:** The following is the code for ex_euler()

      def ex_euler(func, delt, u, a, b, m):

          n=(b-a)/delt+1

          solu=[]
          B=[]

          for i in range(n):
              for j in range(n):
                  B.append(1);
              A.append(B);    
              B=[];

          for i in range(m):
              solu[i][0]=u[i]

          for i in range(1,n):

              fval=func(solu[i-1],(i-1)*delt)

              for j in range(m):

                  solu[i][j]=solu[i-1][j]+delt*fval[j]

      return(solu)

**Last Modified:** March/2018
