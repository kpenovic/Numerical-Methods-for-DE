**Routine Name:**           dot

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will compute the dot product of two python lists.

**Input:** Two python lists of the same length.

**Output:** A scalar that is the dot product of the two lists.

**Usage/Example:**

The routine needs two lists

      a=[1,2,1,2,1]
      b=[1,0,1,0,1]
      
      a=dot(a,b)

Output from the lines above:

      print(b)
      
      3

**Implementation/Code:** The following is the code for dot()

      def dot(a,b):

          if(len(a)>len(b)):
              return(print("Vectors must be same length"))
          if(len(b)>len(a)):
              return(print("Vectors must be same length"))

          n=len(a)

          c=0

          for i in range(n):
              c+=a[i]*b[i]

          return(c)

**Last Modified:** March/2018
