# Controllability and PBH Test

PBH test stands for Popov-Belevitch-Hautus test. It can be use to check the controllability of a plant $\mathbf{A}$ with a controller $\mathbf{B}$.

<code>**Definition**: 
(A, B) is controllable iff rank[(A - $\lambda$) B] = n, $\forall \lambda \in \mathbb{C}$ </code>

Here $\mathbb{C}$ denotes the complex space. 

In this test, we usually only need to enumerate eigenvalues to calculate the rank. 

1. $\text{rank}(\mathbf{A} - \lambda \mathbf{I}) = n$ except for $\lambda$ equals any eigenvalue. If $\lambda$ equals one of the eigenvalues of $\mathbf{A}$, the corresponding eigenvector direction  will be lost for the vector space of $\mathbf{A} - \lambda \mathbf{I}$.

2. It means the augmented matrix $\mathbf{B}$ needs to compensate any direction of the missing eigenvector(s) to recover the vector space of $\mathbf{A}$. 
For example, if the column vectors in $\mathbf{B}$ is only the linear combination of certain eigenvectors but not all, we can easily find an eigenvalue of the direction that $\mathbf{B}$ cannot support thus causing the failure of the PBH test. 
To this end, the column vectors $\mathbf{B}$ should be able to support any of the missing eigenvectors. In other words, the vector(s) $\mathbf{B}$ should contain all eigenvectors, a linear combination of all eigenvectors. 

3. (advance) If $\mathbf{B}$ is a random vector, $(\mathbf{A}, \mathbf{B})$ will be controllable in a high probability. This is related to the compresive sensing, p.s. however not sure why.

4. In rare cases, matrix $\mathbf{A}$ would have more than one eigenvectors (e.g. $k$) have the same eigenvalue $\gamma$. In this case, $\text{rank}(\mathbf{A} - \gamma \mathbf{I}) = n - k$. As a result, we need multiple actuators $u$ and column vectors $\mathbf{B} = [b_1~\dots~b_k]$  to compensate/support the whole vector space of $\mathbf{A}$. 
