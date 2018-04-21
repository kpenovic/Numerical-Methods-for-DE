**Routine Name:**           minfnorm

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine computes the induced matrix infinity norm

**Input:**A matrix

**Output:** A single float value

**Usage/Example:**

To use the function we just need a matrix:
    
    A=[[1,2,3],[4,5,6],[7,8,9]]
    
    minfnorm(A)
    
The output would be:

    24
    
Which is the max row sum as we expect.

**Implementation/Code:** The following is the code for minfnorm()

    def minfnorm(A):
    n=len(A);

    current=0;
    
    for i in range(n):
        temp=0;
        for j in range(n):
            temp+=abs(A[i][j]);
            
        if(temp>current):
            current=temp;
            
    return(current) 
   

**Last Modified:** Febuary/2018
