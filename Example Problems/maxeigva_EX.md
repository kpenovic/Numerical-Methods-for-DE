**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This example goes through to show how the maximum eigenvalue changes in the matrix arrising from the finite difference method applied to the differential equation u''=f(x)

**Usage/Example:**

We can produce this matrix using some basic for-loops, and we can then find the maximum eigen value with the function maxeigva().

    n=20
    tol=.0001
    maxiter=10000
    
    x=[0]*n
    
    for i in range(2,n):
    
        v=[1]*i
        A=[]
        C=[]

        for k in range(i):
            for j in range(i):
                C.append(0);
            A.append(C);
            C=[];
    
    
        for j in range(i-1):
            A[j][j]=-2
            A[j+1][j]=1
            A[j][j+1]=1
            
        A[i-1][i-1]=-2
        
        x[i]=maxeigva(A,v,tol,maxiter)
        
    print(x)
    
    
The output of this will be:


        [0, 1.0000000000000002, 3.4142123182220931, 2.6180338882834149, 3.732030502866825, 3.2469647151265923, 3.847687186105313, 3.532032599898439, 3.9019614053991902, 3.6824097828483997, 3.9316070915276109, 3.7707308801969144, 3.949442196785514, 3.8268479755872917, 3.960996938725847, 3.8645232327895869, 3.9689085737545629, 3.8911590321947997, 3.9744837651953877, 0]
                
We can see from this that the values appear to be approaching 4 as n increases.             
