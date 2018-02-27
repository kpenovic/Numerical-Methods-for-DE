**Author:** Kegan Penovich

**Language:** Python

**Description/Purpose:** This is an example of how to use the condition function to find the pattern in the condition number of the finite difference method for the ODE u''=f(x)

**Example:**

We will create a loop allowing us to find the condition number for many matricies:

      n=20
      tol=.0001
      x=[0]*n

      for k in range(2,n):
         
          A=[]
          C=[]

          for i in range(k):
              for j in range(k):
                  C.append(0);
              A.append(C);
              C=[];

          for j in range(k-1):
              A[j][j]=2
              A[j+1][j]=-1
              A[j][j+1]=-1

          A[k-1][k-1]=-2

          x[k]=condition(A,tol)

This results in the following:

      [0, 0, 1.0000000000000004, 2.7064591496187398, 5.2038578655162375, 8.5206721383014443, 12.660006661163051, 17.619551233704421, 23.397327977871257, 29.990343733344066, 37.398746507441658, 45.619236455938719, 54.653527899054588, 64.496096339628693, 75.156920211402181, 86.616716807866567, 98.906167566048111, 111.97853618734283, 125.89695024529054, 140.57392941353999]

This sugests that the condition number is diverging.

**Last Modified:** Febuary/2018
