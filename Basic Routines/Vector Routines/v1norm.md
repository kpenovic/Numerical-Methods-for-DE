**Routine Name:**           v1norm

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine will compute the 1-norm of a vector.

**Input:** A vector (x).

**Output:** This routine returns a single float value.

**Usage/Example:**

Compute the 1-norm of [1,2,3,4,5,6,7]:

      x=[1,2,3,4,5,6,7]

      v1norm(z)

Output from the lines above:

      28

**Implementation/Code:** The following is the code for v1norm()

    def v1norm(x):
    
    total=0;
    n=len(x);
    
    for i in range(n):
        total+=np.abs(x[i]);
        
    return(total)
      
**Last Modified:** Febuary/2018
