**Routine Name:**           logistic

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine will return the value of the logistic equation given two parameter values and an initial condition at time 0. 
Our parameters come from the Logistic equation when writen as: **dP/dt=aP-bP^2 (1)**

**Input:** There are four imputs to this function: a (value from (1)), b (value from (1)), P_0 (Population at time zero), and t (the time we are interested in).

**Output:** This routine returns a single value that is the population at time t.

**Usage/Example:**

Suppose we have that the conditions a=2.5, b=.01, P_0=100, and t=1. to evaluate this we would do the following:

    import numpy as np
    logistic(2.5,.01,100,1)
    
The result of this is:

    222.59271583988919
    
**Implementation/Code:** The following is the code for logistic(a, b, P_0, t):

    def logistic(a,b,P_0, t):
      #np.abs() is a call out to the numpy library
      #This means to use the program we must import numpy as np
      return(a/(b+(a/P_0-b)*np.exp(-t*a))) 

**Last Modified:** September/2017
