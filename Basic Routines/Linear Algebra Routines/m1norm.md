**Routine Name:**           m1norm

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine computes the induced matrix 1 norm.

**Input:** A matrix.

**Output:** A single float value.

**Usage/Example:**

To use the code we would first need a matrix:

    A=[[1,2,3],[4,5,6],[7,8,9]]
      
    m1norm(A)
    
The output would be:

    18
    
This is the maximum column sum like we would expect

**Implementation/Code:** The following is the code for m1norm()

    def m1norm(A):
        n=len(A);

        current=0;

        for i in range(n):
            temp=0;
            for j in range(n):
                temp+=abs(A[j][i]);

            if(temp>current):
                current=temp;

        return(current)

**Last Modified:** Febuary/2018
