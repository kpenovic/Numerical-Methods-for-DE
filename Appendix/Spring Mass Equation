**Routine Name:**           spmaeq()

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will return the solution to a (potentialy) forced Spring-Mass equation.

**Input:** The 7 imputs are equations the coefficients of the differential opperators (m, c, k), The initial conditions (y_0, v_0), the forcing functions (f(x)), and a time of interest (t).

**Output:** This returns a value representing the position of the spring at time t. 

**Usage/Example:**

Suppose that we have y''+4y=0 as our equation with y_0=0, and v_0=1, and we are then interested at the point t=1.

    spmaeq(1,0,4,0,1,0,1)
    
The output of this would be:

    -0.2080734182735712

**Implementation/Code:** The following is the code for smaceps()

      spmaeq(m, c, k, y_0, y'_0, f(x), t):
        #In each of these a function called 'particular' is called.
        #This function uses variation of parameters to solve for the particular solution.
        #np.abs() is a call out to the numpy library
        #This means to use the program we must import numpy as np
        if(c^2-4*k*m>0):
          a=(-c+np.sqrt(c^2-4*m*k))/(2*m);
          b=(-c-np.sqrt(c^2-4*m*k))/(2*m);
          A=((b*y_0-v_0)/(b-a));
          B=((v_0-a*y_0)/(b-a));
          return(A*np.exp(a*t)+B*np.exp(b*t)+particular(1,a,b,f(x)));
        elseif(c^2-4*k*m<0):
          a=-c/(2*m);
          b=np.sqrt(np.abs(c^2-4*k*m))/(2*m);
          A=y_0;
          B=(v_0-a*y_0)/b;
          return(A*np.exp(a*t)*np.cos(b*t)+B*np.exp(a*t)*np.sin(b*t)+particular(2,a,b,f(x)));
        else:
          a=-c/(2*m);
          A=y_0;
          B=(v_0-y_0)/a;
          return(A*t*np.exp(a*t)+B*np.exp(a*t)+particular(3,a,b,f(x)));
         

**Last Modified:** January/2018
