**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This is an example of how to use various functions to slove an 2D Elliptic PDE of the form: laplacian(u)=f(x,y). We will use the example where f(x,y)=sin(xy) on the unit square with uniformly 0 boundry conditions.
We will do this ussing a 5 point stencil finite difference method (possion2D5()). We will then solve the resulting matrix with an LU decompostion.

**Example:**

    def func(x,y):            # f(x,y)
        return(np.sin(x*y))
        
    mesh=10 # Size of the mesh
    size=1.0 # size of the square over which we are solving
    a = 0    # the x cordinate of botom left corner of the square we are solving over
    b = 0    # the y cordinate of botom left corner of the square we are solving over
    
    A=possion2D5(mesh, func, size, a, b)
    
    B=NaiveLU(A[0])
    
    x=LUsolve(B[0],B[1],A[1])
    
x now holds the solution of the finite difference solution.
We could also solve ith using the Conjugate Gradiant program congrad() as well. This would involve doing the following:
    
    mesh=5             # Size of the mesh
    size=1              # Size of the square over which we are solving
    a=0                 # the x cordinate of botom left corner of the square we are solving over
    b=0                 # the y cordinate of botom left corner of the square we are solving over      
    x=[0]*mesh*mesh     # initial solution guess of all zeros
    n=1000;             # maximum number of iterations
    err=.01             # error tolerance

    B,A=possion2D5(mesh, func, size, a, b)

    cg=congrad(B, A, x, n, err)
    
The output of this would be:

    print(cg)
    [-0.10120331206272884, -0.19228264425909936, -0.257734335260771, -0.2749661431569802, -0.21054713619784152, -0.1674358751840464, -0.31671732192000046, -0.4189577852841041, -0.4412195801557246, -0.32854809734796403, -0.19866411441024254, -0.37278675511155618, -0.49357238854780544, -0.51946897981196416, -0.38554638617887171, -0.18804689843125638, -0.35579136228416669, -0.47376791956757131, -0.50367288078509109, -0.38089496325681177, -0.12745762065266025, -0.24238343576436991, -0.32765946946180563, -0.35688191093190919, -0.28187227238483581]

**Last Modified:** March/2018
