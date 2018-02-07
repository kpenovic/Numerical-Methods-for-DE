**Routine Name:**           elip_int

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will takes imputs of a function, starting and ending point, two boundry conditions and an integer
representing the number of desired itterations. It will return four vectors corresponding to the tridiagonal matrix set-up for a second 
order finite difference approximation.

**Input:** A function (func), starting and ending points (a,b), two boundary conditions (ua, ub), and an itteration number (n) are the 
inputs for this function.

**Output:** This routine returns four vectors. One corresponding to the diagonal of length n, two corresponding to upper and lower diagonal
and the last being the solution vector. These are returned as a tuple.

**Usage/Example:**

Suppose we wish to solve the differential equation: u''=sin(Pi*x), on the interval [0,1] subject to the boundry conditions u(a)=2.5
and u(b)=5.0. We would initialize this problem with our code as follows:

    pi=3.141592653589793238462

    def func(x):
      return(np.sin(pi*x))
    
    a=0
    b=1

    ua=2.5
    ub=5.0

    n=100
    
    res=elip_int(func, a, b, ua, ub, n)

Output from the lines is stored in res as a tuple. The main diagonal is stored in res[0], the upper diagonal in res[1], the lower diagonal 
in res[2], and the solutions vector in res[3]. We can then solve for the approximate values by using a Tridiagonal LU solver like so:

    y=triDiLU(res[0], res[2], res[1], res[3])

    y.insert(0,ua)

    y.append(ub)
    
The vector y now contains the finite difference approximation for this problem. The initial conditions must be appended since the solution only 
contains the approximation on the interior of the bound. The LU code is explained in its own manual entry.

**Implementation/Code:** The following is the code for smaceps()

   def elip_int(func, a, b, ua, ub, n):
    
    d=[] # diagonal
    u=[] # upper diagonal
    l=[] # lower diagonal
    f=[] # function values
    
    
    h=(b-a)/n
    
    for i in range(n):
        d.append(-2);
        
    for i in range(n-1):
        u.append(1);
        l.append(1);
       
    
    f.append(h*h*func(h)-ua)
    
    for i in range(n-2):
        f.append(h*h*func(i*h))
        
    f.append(h*h*func(b-h)-ub)
    
    return(d, u, l, f)

**Last Modified:** Febuary/2018
