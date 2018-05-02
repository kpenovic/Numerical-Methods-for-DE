# Table of Contents

## Appendix 

- [Logistic Equation](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Appendix/Logistic%20Equation.md)
- [Spring Mass Equation](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Appendix/Spring%20Mass%20Equation.md)
- [Basic ODE](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Appendix/ode_basic.md)

## Basic Routines

- Error Computation

  - [Absolute Error (abserr)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Error%20Computation/abserr.md)
  - [Relative Error (relerr)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Error%20Computation/relerr.md)
  - [Relative Error for a vector (vecrelerr)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Error%20Computation/vecrelerr.md)
  
- Linear Algebra Routines
 
  - [LU solver (LUsolve)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/LUsolve.md)
  - [Naive LU decomposition (NaiveLU)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/NaiveLU.md)
  - [Matrix Condition Number (condition)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/condition.md)
  - [Congugate Gradiant Solver (congrad)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/congrad.md)
  - [Gauss Sidel Solver (gauss_Sidel)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/gauss_Sidel.md)
  - [Jacobi Solver (jacobi)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/jacobi.md)
  - [Matrix-1 Norm (m1norm)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/m1norm.md)
  - [Maximum Eigenvalue (maxeigva)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/maxeigva.md)
  - [Maxtrix Infinity Norm (minfnorm)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/minfnorm.md)
  - [Thomas Algorithm Solver (thomas)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/thomas.md)
  - [LU solver on a Tridiagonal Matrix (triDiLU)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/triDiLU.md)
  - [Matrix-Vector Multiplication (vmmult)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Linear%20Algebra%20Routines/vmmult.md)
  
- Vector Routines
 
  - [Vector Subtraction (diff)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Vector%20Routines/diff.md)
  - [Dot Product (dot)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Vector%20Routines/dot.md)
  - [Scalar Multiplication (scamult)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Vector%20Routines/scamult.md)
  - [Vector-1 norm (v1norm)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Vector%20Routines/v1norm.md)
  - [Vector-2 norm (v2norm)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Vector%20Routines/v2norm.md)
  - [Vector Infinity Norm (vinfnorm)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Vector%20Routines/vinfnorm.md)
  - [Copy Vector (vcopy)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Vector%20Routines/vcopy.md)
  
- [Compute Machine Error (Machine Epsilon)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/Machine%20Epsilon.md)
- [Coefficients for finite difference methods (fdcoeff)](https://github.com/kpenovic/Numerical-Methods-for-DE/blob/master/Basic%20Routines/fdcoeff.md)

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
