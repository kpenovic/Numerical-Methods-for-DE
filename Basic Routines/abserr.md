**Routine Name:**           abserr

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine will compute the absolute error bettween an approximate value and a actual value.

**Input:** Imputs are aprx (approximate value) and actl (actual value).

**Output:** This routine returns a float that is absolute value the difference bettween the actual and approximate value.

**Usage/Example:**

Suppose I have two values, 1.23452434 and 1.2334563 where the first is a guess of the second. I wish to know what the absolute value of the difference between them is.
We can do this by the following: 

      import numpy as np
      
      abserr(1.23452434,1.2334563)

Output from the lines above:

      0.0010681400000001062

**Implementation/Code:** The following is the code for abserr(actl, aprx)

      def abserr(aprx, actl):
        #np.abs() is a call out to the numpy library
        #This means to use the program we must import numpy as np
        return np.abs(aprx-actl)
        

**Last Modified:** January/2018
