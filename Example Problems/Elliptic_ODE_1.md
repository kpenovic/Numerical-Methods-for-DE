**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This is an example of how to use various functions to slove an ODE of the form: u''=f(x) 
and then estimate the error compared to the real solution. The Example is u''=sin(Pi*x) on [0,1], ua=2.5, ub=5.0.

**Example:**
      pi=3.141592653589793238462

      def func(x):
          return(np.sin(pi*x))

      def solu(x):
          return(-np.sin(pi*x)/(pi*pi)+2.5*x+2.5);

      a=0
      b=1

      ua=2.5
      ub=5.0

      n=100 # number of itterations

      x=[0]*(n+2);

      res=elip_int(func, a, b, ua, ub, n);

      for i in range(1,n+2):
          x[i]=a+i*(1/(n+1));

      ytrue=[0]*(n+2)

      for i in range(0,(n+2)):

          ytrue[i]=solu(x[i]);

      y=triDiLU(res[0], res[2], res[1], res[3])

      y.insert(0,ua);

      y.append(ub);

      vecrelerr(y, ytrue, 1) # relative error in the 1-norm
      vecrelerr(y, ytrue, 2) # relative error in the 2-norm
      vecrelerr(y, ytrue, 0) # relative error in the infinity norm

This results in the following:

      0.0092578572593 # relative error in the 1-norm
      0.0403513867038 # relative error in the 2-norm
      0.198           # relative error in the infinity norm

**Last Modified:** Febuary/2018
