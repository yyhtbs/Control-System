# 课程目标：

1. 如何计算一个线性系统的响应
2. 如何通过对角化来简化计算

一个动态系统的状态空间表示：
$$\dot{x}=\mathbf{A}x, x \in \mathbb{R}^n$$

这个微分方程的解析表达式：
$$x(t)=e^{\mathbf{A}t}x(0)$$

由于$x(0)$是一个常量，需要计算的是$e^{\mathbf{A}t}$,
通过泰勒展开，可以计算，
$$e^{\mathbf{A}t} = I + \mathbf{A}t + \frac{\mathbf{A}^2t^2}{2!} + \cdots$$

实际上$e^{\mathbf{A}t}$这个东西不太好算，所以需要一些变换来降运算量。
需要从$\mathbf{A}$下手（主要就是要把它变成一个对角矩阵）。
所以考虑把$x$进行投射，映射到一个简单的空间上去。这个简单的空间就是特征（Eig）空间。之后我们会看见，在这个空间上的控制状态是解耦的。

$x$是原始空间的状态，$z$是特征空间的状态。

首先对状态转移矩阵进行特征分解：
$$\mathbf{A}\xi = \lambda \xi$$
令 $\Tau=[\xi_1 \dots \xi_n]$，和$\mathbf{D} = \begin{bmatrix}
\lambda_1 &   &  \\
  & \ddots &  \\
  &   & \lambda_n
\end{bmatrix}$,
其中，每一个$\xi$是特征向量。

我们可以得到$\mathbf{A}\Tau = \Tau\mathbf{D}$和$\mathbf{A} = \Tau^{-1}\Tau\mathbf{D}$

通过$\Tau$我们把$x$的坐标进行变换，$ x = \Tau z$

因为$ \dot{x} = \Tau \dot{z}$且$\dot{x}=\mathbf{A}x$且$x=\Tau z$，所以$\Tau \dot{z} = \mathbf{A}\Tau z$，
进一步推导，$\dot{z} = \Tau^{-1} \mathbf{A}\Tau z$
$\dot{z} = \text{D} z$，因为$\Tau^{-1} \mathbf{A}\Tau = \text{D}$

因为$\text{D}是对角矩阵$，$\dot{z} = \text{D} z$的优点是每一个变量都被解耦了，即$\dot{z_n} = \lambda_nz_n$。使得系统更好分析，更好计算。
$$\frac{d}{dt} 
\begin{bmatrix} z_1\\ \vdots \\z_n\end{bmatrix} 
= \begin{bmatrix} \lambda_1 &   &  \\ & \ddots &  \\ &   & \lambda_n
\end{bmatrix} \begin{bmatrix} z_1\\ \vdots \\z_n\end{bmatrix} 
$$

在特征空间，系统的状态空间方程如下，
$z(t) = r^{\Delta t}z(0) = \begin{bmatrix} e^{\lambda_1} &   &  \\ & \ddots &  \\ &   & e^{\lambda_n}
\end{bmatrix} z(0)$

讲师说，他总是把一个系统隐射到特征空间进行处理，因为这样更简单。

## 映射回去




\\
\\
\\
\\