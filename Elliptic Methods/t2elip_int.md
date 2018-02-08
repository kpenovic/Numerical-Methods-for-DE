**Routine Name:**           t2elip_int

**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This routine initializes the vectors needed to use finite difference methods on the Elliptic ODE: d/dx(k(x)du/dx)=f(x).

**Input:**The k(x) function (func1) A function f(x) (func2), starting and ending points (a,b), two boundary conditions (ua, ub), 
and an itteration number (n) are the inputs for this function.

**Output:** This routine returns four vectors. One corresponding to the diagonal of length n, two corresponding to upper and 
lower diagonal and the last being the solution vector. These are returned as a tuple.

**Usage/Example:**

To implement the situation in Problem 9 we would just nee to define func1 as follows and then feed it into the function

    def k(x):
      return(uniform(10,50))
      
    t2elip_int(k, func2, a, b, ua, ub, n):
    
We ould now only need to have the rest of the set up to initialize this problem.

**Implementation/Code:** The following is the code for t2elip_int()

    def t2elip_int(func1, func2, a, b, ua, ub, n):
      d=[]*n # diagonal
      u=[]*(n-1) # upper diagonal
      l=[]*(n-1) # lower diagonal
      f=[]*n # function values
    
    h=(b-a)/n
    
    for i in range(n):
        d[i]=-(func1((i-0.5)*h)+func1((i+0.5)*h));
        
    for i in range(n-1):
        u[i]=func1((i+0.5)*h);
        l[i]=func1((i-0.5)*h);
        
    f[0]=(h*h*func2(h)-ua)
    
    for i in range(1,n-1):
        f[i]=(h*h*func2(i*h))
        
    f[n-1]=(h*h*func(b-h)-ub)
    
    return(d, u, l, f) 

**Last Modified:** Febuary/2018
