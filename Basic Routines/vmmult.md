**Routine Name:**           vmmult

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will compute the product of a matrix and a vector.

**Input:** A matrix (A) and a vector (b).

**Output:** A single vector.

**Usage/Example:**

The routine needs a matrix and a vector.

      A=[[1,2,3],[4,5,6],[7,8,9]]
      b=[1,1,1]
      
      c=vmmult(A,b)

Output from the lines above:

      print(c)
      
      [6,15,24]
     
**Implementation/Code:** The following is the code for vmmult()

      def vmmult(A,b):

          if(len(A)>len(b)):
              return(print("Lengths must be compatible"))
          if(len(b)>len(A)):
              return(print("Lengths must be compatible"))

          n=len(A)

          c=[0]*n

          for i in range(n):
              for j in range(n):
                  c[i]+=A[i][j]*b[j]

          return(c)

**Last Modified:** March/2018
