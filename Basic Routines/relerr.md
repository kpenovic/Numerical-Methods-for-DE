**Routine Name:**           relerr

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine will compute the relative error between an approximate value and a true value.

**Input:** The function requires two imputs: aprx (approximate value) and actl (actual value).

**Output:** This routine returns a float that is the percent error between the approximate value and the actual value.

**Usage/Example:**

Suppose that we want to know what the relative error is between the approximate value 1.23452434 and the actual value 1.2334562.

    relerr(1.23452434,1.2334562)
   
The output of this is:

    0.00086597318980609621    

**Implementation/Code:** The following is the code for smaceps()

      def relerr(aprx,actl):
        return(np.abs((actl-aprx)/actl))

**Last Modified:** January/2018
