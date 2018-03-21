**Routine Name:**           vcopy

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will copy the contents of one list into another. The "=" opperator only creates a pointer to, not a copy of, the target list so this needed in some cases.

**Input:** a vector you wish to copy.

**Output:** This routine returns a list that is a copy of the input list.

**Usage/Example:**

The routine needs a list to copy.
      
      a=[1,2,3,4,5]
      
      b=vcopy(a)

Output from the lines above:

      print(b)
      
      [1,2,3,4,5]

**Implementation/Code:** The following is the code for vcopy()

      def vcopy(a):

          n=len(a)

          c=[0]*n

          for i in range(n):
              c[i]=a[i]

          return(c)

**Last Modified:** March/2018
