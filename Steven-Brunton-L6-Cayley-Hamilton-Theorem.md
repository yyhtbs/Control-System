# Cayley-Hamilton Theorem

In linear algebra, the Cayley–Hamilton theorem (named after the mathematicians Arthur Cayley and William Rowan Hamilton) states that every square matrix over a commutative ring (such as the real or complex field) satisfies its own characteristic equation.

For (almost) any matrix A, it satisify $|\mathbf{A} - \lambda \mathbf{I}| = 0$. For example a $3\times3$ matrix, the solution to $|\mathbf{A} - \lambda \mathbf{I}| = 0$ is

$$\lambda^3 + (tr(\mathbf{A})\lambda^2)+dm(\mathbf{A})\lambda + |\mathbf{A}| = 0$$

Here, $tr$ means the trace and $dm$ means the minors of the terms at the leading diagnal of $\mathbf{A}$.   

After simplying the equation, we can have a general form, $$a_1 \lambda^3 + a_2 \lambda^2 + a_3 \lambda + a_4 = 0$$
What does Cayley-Hamilton theorem said is by replacing $\lambda$ by $\mathbf{A}$ the simplified equation still holds, 
$$a_1 \mathbf{A}^3 + a_2 \mathbf{A}^2 + a_3 \mathbf{A} + a_4 = 0$$

## Application in Matrix Operation

Example: calculate $\mathbf{A}^{-1}$
By multiplexing the both ends of the simplified equation by $\mathbf{A}^{-1}$, we can get
$$a_1 \mathbf{A}^2 + a_2 \mathbf{A}^1 + a_3 + a_4 \mathbf{A}^{-1} = 0 \\\mathbf{A}^{-1} = \frac{-a_1 \mathbf{A}^2 - a_2 \mathbf{A}^1 - a_3}{ a_4 }$$

## Application in Control System - Order Reduction

### Represent Higher Order Terms using Low Order Combinations

For any matrix $\mathbf{A}$, it always satisfies $|\mathbf{A}-\lambda\mathbf{I}| = 0$
By expanding it, we will get

$$\lambda^n+a_{n-1}\lambda^{n-1}+\cdots+a_{1}\lambda+a_0 = 0$$

According to Cayley-Hamilton theorem the equation still holds if we replace $\lambda$ by $\mathbf{A}$. By simplify it, we will get

$$\mathbf{A}^n+a_{n-1}\mathbf{A}^{n-1}+\cdots+a_{1}\mathbf{A}+a_0\mathbf{I} = 0\\
\mathbf{A}^n = -a_{n-1}\mathbf{A}^{n-1}-\cdots-a_{1}\mathbf{A}-a_0\mathbf{I}\\
\mathbf{A}^{n+1} = -a_{n-1}\mathbf{A}^{n}-\cdots-a_{1}\mathbf{A}^2-a_0\mathbf{A}\\
\mathbf{A}^{n+1} = -a_{n-1}(-a_{n-1}\mathbf{A}^{n-1}-\cdots-a_{1}\mathbf{A}-a_0\mathbf{I})-\cdots-a_{1}\mathbf{A}^2-a_0\mathbf{A}\\=-\alpha_{n-1}\mathbf{A}^{n-1}-\cdots-\alpha_{1}\mathbf{A}^2-\alpha_0\mathbf{A}\\
\dots$$
We can see that for higher ordera $\forall k > n$, the power of matrix $\mathbf{A}$ can be represented by the linear combination of lower orders, as shown below
$$\mathbf{A}^{k} = -\alpha_{n-1}\mathbf{A}^{n-1}-\cdots-\alpha_{1}\mathbf{A}^2-\alpha_0\mathbf{A}$$

### Reduce from Infinite Terms to Finite Terms

For a dynamic system $\dot{x}= \mathbf{A}x$, its close loop solution is $e^{\mathbf{A}t}x(0)$ in which
$$e^{\mathbf{A}t} = \mathbf{I}+\mathbf{A}t+\frac{\mathbf{A}^2t^2}{2!}+\cdots\\$$
Since the higher order terms ($\geq n$)  can be represented by the lower order ($\leq n-1$) terms, the inifinite representation can be rewritten to a finite combination, 
$$e^{\mathbf{A}t} = \phi_0(t)\mathbf{I}+\phi_1(t)\mathbf{A}+\cdots +\phi_{n-1}(t)\mathbf{A}^{n-1}$$

## Application in Control System - Reachability and Controllability


