# Controllability and Reachability

For a **linear** system, there are three equivalent ways to check the controllability:

## Controllability

We have a system, $\dot{x} = \mathbf{A}x+\mathbf{B}u$

The system is controllable if the controllability matrix is full rank, i.e.
$$\mathcal{C} = [\mathbf{B}~~\mathbf{AB}~~\cdots~~\mathbf{A}^{n-1}\mathbf{B}]$$

In Matlab, a single line of command is available to check the controllability: 
<div align="center"> <code> rank(ctrb(A, B)) </code> </div>

## Arbitrary Eigenvalue Placement: 

If we have $u = -Kx$, such that the close-loop system $\dot{x} = (\mathbf{A}-K\mathbf{B})x$ have arbitrary eigenvalue respect with $\mathbf{A}-K\mathbf{B}$, it means the system is controllable.

## Arbitrary Reachability: 

Let us define a reachable set for the state $x$: $R_t=\{\xi \in \mathbb{R}^n|\exist u(t): x(t) \rightarrow \xi\}$. If this set covers the whole state space $R_t= \mathbb{R}^n$, the linear system is controllable.

## Why the state can be "arbitrarily" reachable?

If the the system is controllable, it means existing a function to cover the whole space. As mentioned in the previous lecture (Gramians), given a finite amount of energy, the controller can place the state anywhere on an ellipse. Also because the system is linear, it is possible to add/reduce energy (dec/increase $K$) to scale the ellipse. So by scalling the ellipse, all points on the scaled ellipses will cover the whole space, i.e. the state can reach anywhere. 