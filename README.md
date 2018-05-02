# Table of Contents

## Appendix 

- Logistic Equation
- Spring Mass Equation
- Basic ODE

## Basic Routines

- Error Computation

  - [Absolute Error (abserr)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Appendix/Logistic%20Equation.md)
  - Relative Error (relerr)
  - Relative Error for a vector (vecrelerr)
  
- Linear Algebra Routines
 
  - LU solver (LUsolve)
  - Naive LU decomposition (NaiveLU)
  - Matrix Condition Number (condition)
  - Congugate Gradiant Solver (congrad)
  - Gauss Sidel Solver (gauss_Sidel)
  - Jacobi Solver (jacobi)
  - Matrix-1 Norm (m1norm)
  - Maximum Eigenvalue (maxeigva)
  - Maxtrix Infinity Norm (minfnorm)
  - Thomas Algorithm Solver (thomas)
  - LU solver on a Tridiagonal Matrix (triDiLU)
  - Matrix-Vector Multiplication (vmmult)
  
- Vector Routines
 
  - Vector Subtraction (diff)
  - Dot Product (dot)
  - Scalar Multiplication (scamult)
  - Vector-1 norm (v1norm)
  - Vector-2 norm (v2norm)
  - Vector Infinity Norm (vinfnorm)
  - Copy Vector (vcopy)
  
- Compute Machine Error (Machine Epsilon)
- Coefficients for finite difference methods (fdcoeff)

## Elliptic Methods

- Elliptical ODE Finite Difference Matrix (constant k)  (elip_int)
- Elliptical ODE Finite Difference Matrix (function k)  (elip_int)
- Elliptical PDE 5-Point Mesh (possion2D5) 
- Elliptical PDE 9-Point Mesh (possion2D5) 

## Example Problems

- Elliptical PDE 5-Point Mesh Demo (2DEllipticSolver5point_EX)
- Elliptical PDE 9-Point Mesh Demo (2DEllipticSolver9point_EX)
- Elliptic ODE Demo (Eliptic_ODE_1_EX)
- Parabolic ODE Explicit Euler Demo (ex_euler_demo)
- Parabolic ODE Implicit Euler Demo (im_euler_aut)
- Parabolic ODE RK2 Demo (RK2_aut_demo)
- Parabolic ODE RK4 Demo (RK4_aut_demo)
- Parabolic ODE Predictor Corrector Demo (ODE43_aut_demo)
- Hyperbolic PDE Upwinding Method Demo (upwing_Demo)
- Hyperbolic PDE Lax-Wendroff Method Demo (laxWendroff_Demo)
- Hyperbolic PDE Beam-Warming Method Demo (BeamWarming_Demo)
- Stability of Explicit Euler
- Stability of Implicit Euler
- Stability of Implicit Euler for increasing time step
- Stability of Multi-Step Method
- Stability of RK4 Method
- Efficiency comparison of Jacobi, Gauss-Sidel, and Conjugate Gradient methods (Ja_Gs_Cg_Comparison)
- Condition Number of a matrix demo (condition_EX)
- Maximum Eigenvalue Demo (maxeig_EX)

## Hyperbolic Methods

- Hyperbolic PDE Upwinding Method (upwinding)
- Hyperbolic PDE Lax-Wendroff Method (LaxWendroff)
- Hyperbolic PDE Beam-Warming Method (BeamWarming)

## Parabolic Methods

- Parabolic ODE Explicit Euler Demo (ex_euler)
- Parabolic ODE Implicit Euler Demo (im_euler)
- Parabolic ODE RK2 Demo (RK2_aut)
- Parabolic ODE RK4 Demo (RK4_aut)
- Parabolic ODE Predictor Corrector Demo (ODE43_aut)
- Parabolic PDE Explicit Euler Demo (exEulerPDE)
