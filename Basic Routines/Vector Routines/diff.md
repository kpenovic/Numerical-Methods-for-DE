**Routine Name:**           diff

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will compute the difference between 2 python lists.

**Input:** The imput is two python lists

**Output:** A single list containing the difference between the two input lists. 

**Usage/Example:**

The routine need only be called and given the particular float type you are looking for.

      a=[1,2,3,4,5]
      b=[2,3,4,5,6]
      
      c=diff(a,b)

Output from the lines above:

      print(c)
      
      [-1,-1,-1,-1,-1]

**Implementation/Code:** The following is the code for diff()

      def diff(a,b):

          if(len(a)>len(b)):
              return(print("Vectors must be same length"))
          if(len(b)>len(a)):
              return(print("Vectors must be same length"))

          n=len(a)

          c=[0]*n

          for i in range(n):
              c[i]=a[i]-b[i]

          return(c)

**Last Modified:** March/2018
