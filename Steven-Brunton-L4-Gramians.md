# Gramian
Gramian is a better way to describe the controllability of a dynamic system, i.e. It allows describing the level of controllability for different states $x$. 

# How?
The calculation of gramian is as simple as performing eigenvalue decomposition of the controllability matrix $\mathcal{C}$. 
<code>SVD($\mathcal{C}$)</code>

# The close form solution for controlled system
The solution of a controlled plant $\dot{x} = \mathbf{A}x+\mathbf{B}u$ is 

$$x(t) = e^{\mathbf{A}t}x(0) + \int^t_0{e^{\mathbf{A}(t - \tau)}\mathbf{B}u(\tau)}d \tau$$

Here, the second term can be viewed as the convolution of $e^{\mathbf{A}t}$ and $u(t)$, i.e. viewing $\mathbf{B}u(t)$ as the convolution kernel applying on $e^{\mathbf{A}t}$.

# Controllability Gramian

The formal way to calculate Gramian is 
$$W_t = \int^t_0{e^{\mathbf{A}\tau}\mathbf{B}\mathbf{B}^*e^{\mathbf{A*}\tau}}d\tau \in \mathbb{R}^{n \times n}$$

In this example, $W_t$ is a symetric matrix in real number field $\mathbb{R}^{n\times n}$, means its eigen value is always non-negative. 

Via Eigenvalue Decomposition, we will have, 
$$W_t \xi = \lambda \xi$$
After sorting the eigenvalues, the eigenvector corresponding to the largest eigenvalue has the highest controllability in the **state space**. The physical meaning of the highest controllability is that by using the minimum energy the controller can produce the greatest response.

# Analogy in Discrete Time System (For Illustration Purpose)


For a discrete time system, the symmetric matrix becomes $W_t \approx \mathcal{C}\mathcal{C}^*$

We can see $W_t$ is the singlular value decomposition of $\mathcal{C}$：

$$[\text{U}, \Sigma, \text{V}] = svd(\mathcal{C}, \text{'ecom'})$$

Here the eigenvalue $\lambda$ of $W_t$ is the square of the singular value $\Sigma$. The eigenvector $\xi$ is the column vector of the singular matri $\text{U}$. Therefore, the first column of the singular matrix corresponds to the highest eigenvalue, means it is the easiest to be controlled. The second column is the second easiest controllable vector. And so on, until the most uncontrollable amount.

## Graph Illustration

An example is given the following figure $\xi_1$ is the direction (eigen-state) that can be easiest controlled while $\xi_2$ is the the most difficult eigen-state to be controlled.

![](./ellipsoid.png)

Given a finit energy, the controllability can It can move along the edge of this ellipse, and the distance from the point to the origin refers to the degree of controllability.

Example: For example, a person can control the car to drive forward and backward easily, however sideways parking is difficult. Through singular value decomposition, the controllability of a different state can be found.
