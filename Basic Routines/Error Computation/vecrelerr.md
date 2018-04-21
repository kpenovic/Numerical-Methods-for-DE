**Routine Name:**           vecrelerr

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine will compute the 1, 2 or infity normed relative error between two vectors.

**Input:** An aproximate vector (aprx), The actual vector (actl), and 1, 2, or 0 (infinity) for the norm you wish to use.

**Output:** This routine returns a single float value.

**Implementation/Code:** The following is the code for v2norm()

    def vecrelerr(aprx, actl, norm):
    
    if(len(x)!=len(y)):
        return("Vectors must be the same length");
    
    if(norm==1):
        return(v1norm(z)/v1norm(y));
    elif(norm==2):
        return(v2norm(z)/v2norm(y));
    elif(norm==0):
        return(vinfnorm(z)/vinfnorm(y));
    else:
        return("Imput: 1, 2, or 0");
      
**Last Modified:** Febuary/2018
