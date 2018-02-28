**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This is an example of how to use various functions to slove an 2D Elliptic PDE of the form: laplacian(u)=f(x,y). We will use the example where f(x,y)=sin(xy) on the unit square with uniformly 0 boundry conditions.
We will do this ussing a 5 point stencil finite difference method (possion2D5()). We will then solve the resulting matrix with an LU decompostion.

**Example:**

    def func(x,y):            # f(x,y)
        return(np.sin(x*y))
        
    mesh=100 # Size of the mesh
    size=1.0 # size of the square over which we are solving
    a = 0    # the x cordinate of botom left corner of the square we are solving over
    b = 0    # the y cordinate of botom left corner of the square we are solving over
    
    A=possion2D5(mesh, func, size, a, b)
    
    B=NaiveLU(A[0])
    
    x=LUsolve(B[0],B[1],A[1])
    
x now holds the solution of the finite difference solution.    


**Last Modified:** Febuary/2018
