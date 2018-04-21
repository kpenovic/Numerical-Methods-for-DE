**Routine Name:**           scamult

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will multiply each element of a python list by a scalar value.

**Input:** The input of the function is a list and a scalar value.

**Output:** A list containing the input list multiplied by the scalar value.

**Usage/Example:**

The routine needs a list and a scalar value.

      a=[1,2,3,4,5]
      b=2
      
      c=scamult(a,b)
   

Output from the lines above:

      print(c)
      
      [2,4,6,8,10]

**Implementation/Code:** The following is the code for scamult

      def scamult(a,b):
          n=len(b)

          c=[0]*n

          for i in range(n):
              c[i]=a*b[i]

          return(c)

**Last Modified:** March/2018
