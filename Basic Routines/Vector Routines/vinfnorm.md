**Routine Name:**           vinfnorm

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine will compute the infinity-norm of a vector.

**Input:** A vector (x).

**Output:** This routine returns a single float value.

**Usage/Example:**

Compute the infinity-norm of [1,2,3,4,5,6,7]:

      x=[1,2,3,4,5,6,7]

      vinfnorm(x)

Output from the lines above:

      7

**Implementation/Code:** The following is the code for vinfnorm()

    def vinfnorm(x):
    
    x=np.abs(x);
    current=x[0];
    n=len(x);
    
    for i in range(1,n):
        if(current<x[i]):
            current=x[i];
    
    return(current)
      
**Last Modified:** Febuary/2018
