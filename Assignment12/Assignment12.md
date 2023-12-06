Matrix Theory: Assignment 12 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 12. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.

## Question 1
Given $\mathbf{G} = \mathbf{A}^T\mathbf{A}$ where $\mathbf{A} \in \mathbb{R}^{m \times n}$ with $m \ge n$. Now

$$
\begin{align*}
\mathbf{G}^T &= (\mathbf{A}^T\mathbf{A})^T \\
&= \mathbf{A}^T\mathbf{A} \\
&= \mathbf{G} \\
\end{align*}
$$

i.e., $\mathbf{G}$ is a symmetric matrix $\in \mathbb{R}^{n \times n}$. Let $\lambda$ be an eigenvalue of $\mathbf{G}$ for the non-zero eigen vector $\mathbf{x}.$

$$
\begin{align*}
\mathbf{Gx} &= \lambda \mathbf{x} \\
\implies \mathbf{A}^T \mathbf{Ax} &= \lambda \mathbf{x} \\
\implies \mathbf{x}^T \mathbf{A}^T \mathbf{Ax} &=  \mathbf{x}^T \lambda \mathbf{x} \\
\implies \lVert \mathbf{Ax} \rVert^2_2 &= \lambda \lVert \mathbf{x} \rVert^2_2 \\
\implies \lambda &= {\lVert \mathbf{Ax} \rVert^2_2 \over \lVert \mathbf{x} \rVert^2_2} \\
\end{align*}
$$

$\lambda$ must be both real and non-negative to satisfy the above equation with $\lambda = 0$ iff $\lVert \mathbf{x} \rVert^2_2 = 0$. But this contradicts the assumption that $\mathbf{x}$ is a non-zero vector. Thus the eigenvalues of $\mathbf{G}$ are real and positive.

## Question 2
Let any matrix $\mathbf{A}\in\mathbb{R}^{m\times n}$ with rank $r$. Let $\mathbf{v}_1 \in \mathbb{R}^n$ be an unit vector in the row space of $\mathbf{A}$. Corresponding to $\mathbf{v}_1$ we can find a vector $\mathbf{u}_1$ which is an unit vector such that 

$$
\begin{align*}
\mathbf{Av}_1 = \sigma_1\mathbf{u}_1
\end{align*}
$$

where $\sigma_1$ will handle the scaling of the vector and $u_1$ is the direction of the vector. 

As we know that $r = \mathrm{dim}(C(A)) = \mathrm{dim}(R(A))$, so taking an orthonormal basis of $R(A)$ i.e. $\set{\mathbf{v}_1, \cdots, \mathbf{v}_r}$, we can find vectors $\set{\mathbf{u}_1, \cdots, \mathbf{u}_r}$ such that 

$$
\mathbf{A}\mathbf{v}_i = \sigma_i \mathbf{u}_i\quad  \forall i = 1, \cdots, r
$$

Similarly finding the orthonormal basis of $N(A)$ i.e. $\set{\mathbf{v} _ {r+1}, \cdots, \mathbf{v} _ n}$, we can find vectors $\set{\mathbf{u}_{r+1}, \cdots, \mathbf{u}_n}$ such that

$$
\mathbf{A}\mathbf{v}_i = \sigma_i \mathbf{u}_i\quad  \forall i = r+1, \cdots, n
$$

Now, we can write the SVD of $\mathbf{A}$ as

$$
\begin{align*}
\mathbf{A} &= \mathbf{U\Sigma V}^T \\
&= \begin{bmatrix}\mathbf{u} _ 1 & \cdots & \mathbf{u} _ r & \mathbf{u} _ {r+1} & \cdots & \mathbf{u} _ n\end{bmatrix}\begin{bmatrix}\sigma _ 1 & \cdots & 0 & 0 & \cdots & 0 \\\ \vdots & \ddots & \vdots & \vdots & \ddots & \vdots \\\ 0 & \cdots & \sigma _ r & 0 & \cdots & 0 \\\ 0 & \cdots & 0 & 0 & \cdots & 0 \\\ \vdots & \ddots & \vdots & \vdots & \ddots & \vdots \\\ 0 & \cdots & 0 & 0 & \cdots & 0\end{bmatrix}
\begin{bmatrix}\mathbf{v}^T _ 1 \\\ \vdots \\\ \mathbf{v} _ r ^T \\\ \mathbf{v} _ {r+1}^T \\\ \vdots \\\ \mathbf{v} _ n^T\end{bmatrix} \\
&= \begin{bmatrix}\mathbf{u} _ 1 & \cdots & \mathbf{u} _ r & \mathbf{u} _ {r+1} & \cdots & \mathbf{u} _ n\end{bmatrix}\begin{bmatrix}\sigma _ 1 & \cdots & 0 \\\ \vdots & \ddots & \vdots \\\ 0 & \cdots & \sigma_r \\\ 0 & \cdots & 0 \\\ \vdots & \ddots & \vdots \\\ 0 & \cdots & 0\end{bmatrix}\begin{bmatrix}\mathbf{v} _ 1^T \\\ \vdots \\\ \mathbf{v} _ r^T\end{bmatrix} \\
&= \begin{bmatrix}\mathbf{u} _ 1 & \cdots & \mathbf{u} _ r\end{bmatrix}\begin{bmatrix}\sigma _ 1 & \cdots & 0 \\\ \vdots & \ddots & \vdots \\\ 0 & \cdots & \sigma _ r\end{bmatrix}\begin{bmatrix}\mathbf{v} _ 1^T \\\ \vdots \\\ \mathbf{v} _ r^T\end{bmatrix} \\
&= \sum_{i=1}^r \sigma _ i \mathbf{u} _ i \mathbf{v} _ i^T
\end{align*}
$$

Thus, we can say that $\set{\mathbf{u}_1, \cdots, \mathbf{u}_r}$ and $\set{\mathbf{v}_1, \cdots, \mathbf{v}_r}$ are the left and the right singular matrices respectively. 

Claim: We can choose the set $\set{\mathbf{v}_1, \cdots, \mathbf{v}_r}$ such that they are the eigenvectors of $\mathbf{A}^T\mathbf{A}$.

Proof: As $\mathbf{A}^T \mathbf{A}$ is a symmetric matrix we can use spectral theorem and say that $\mathbf{A}^T \mathbf{A}$ is diagonalizable, and we can write it as

$$
\begin{align*}
\mathbf{A}^T \mathbf{A} &= \mathbf{V} \mathbf{\Lambda} \mathbf{V}^T \\
\end{align*}
$$

where $\mathbf{V}$ is the matrix of eigenvectors of $\mathbf{A}^T \mathbf{A}$ and $\mathbf{\Lambda}$ is the diagonal matrix of eigenvalues of $\mathbf{A}^T \mathbf{A}$ and $\mathbf{V}$ is an orthogonal matrix. 

As $\mathrm{rank}(\mathbf{A}) = \mathrm{rank}(\mathbf{A}^T \mathbf{A})$, we take the eigenvectors corresponding to the non-zero eigenvalues of $\mathbf{A}^T \mathbf{A}$ and normalize them to get the set $\set{\mathbf{v}_1, \cdots, \mathbf{v}_r}$.

<p align='right'>$\square$</p>

Now, we have defined our right singular values as eigenvectors of $\mathbf{A}^T \mathbf{A}$, which are orthogonal to each other. Thus, we can say that $\mathbf{v}_i^T \mathbf{v}_j = 0$ for $i \ne j$.

Finding the dot product of left singular vectors

$$
\begin{align*}
\langle \mathbf{u}_i, \mathbf{u}_j \rangle &= \left\langle \left(\mathbf{A v}_i \over \sigma_i\right), \left(\mathbf{A v}_j \over \sigma_j\right)\right\rangle\\
&= {1\over \sigma_i\sigma_j}\mathbf{v}_i^T \mathbf{A}^T \mathbf{A}  \mathbf{v}_j \\
&= {1\over \sigma_i\sigma_j}\mathbf{v}_i^T \lambda_j \mathbf{v}_j \\
&= {1\over \sigma_i\sigma_j}\lambda_j \mathbf{v}_i^T \mathbf{v}_j \\
&= \begin{cases} 0 & i \ne j \\ {\lambda_j \over \sigma_i\sigma_j} & i = j \end{cases}
\end{align*}
$$

Thus, the left singular vectors are also orthogonal to each other.

<p align='right'>$\square$</p>

## Question 3

$a)$ Let $\mathbf{A} \in \mathbb{R}^{m \times n}$ and $\mathbf{x} \in \mathbb{R}^{n}$

$$
\mathbf{A}=\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn} \\
\end{bmatrix}
$$

$$
\mathbf{x}=\begin{bmatrix}
x_1 \\
x_2 \\
\vdots  \\
x_n \\
\end{bmatrix}
$$

$$
\mathbf{Ax}=\begin{bmatrix}
a_{11}x_1+a_{12}x_2+\cdots + a_{1n}x_n \\
a_{21}x_1+a_{22}x_2+\cdots + a_{2n}x_n \\
\vdots  \\
a_{m1}x_1+a_{m2}x_2+\cdots + a_{mn}x_n \\
\end{bmatrix} = \begin{bmatrix} \displaystyle\sum_{i=1}^n a_{1i}x_i\\\  \displaystyle\sum_{i=1}^n a_{2i}x_i\\\ \vdots \\\  \displaystyle\sum_{i=1}^n a_{mi}x_i\end{bmatrix}
$$

Notice, each entry of $\mathbf{Ax}$ is a scalar. Let each of its entries be $y_i.$ Thus, we have:

$$
\mathbf{Ax}=\begin{bmatrix}
y_1 \\
y_2 \\
\vdots  \\
y_m \\
\end{bmatrix}
$$

$$
\frac{\partial{\mathbf{Ax}}}{\partial{\mathbf{x}}}=\begin{bmatrix}
\frac{\partial{y_1}}{\partial{\mathbf{x}}} \\
\frac{\partial{y_2}}{\partial{\mathbf{x}}}  \\
\vdots  \\
\frac{\partial{y_m}}{\partial{\mathbf{x}}}  \\
\end{bmatrix}
$$

$$
\begin{align*}
\frac{\partial{y_i}}{\partial{\mathbf{x}}}=\begin{bmatrix}\displaystyle\frac{\partial{y_i}}{\partial{{x_1}}}& \displaystyle\frac{\partial{y_i}}{\partial{{x_2}}}& \cdots & \displaystyle\frac{\partial{y_i}}{\partial{{x_n}}} \end{bmatrix}
\end{align*}
$$


Therefore,

$$
\frac{\partial{\mathbf{Ax}}}{\partial{\mathbf{x}}}=\begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn} \\
\end{bmatrix}=\mathbf{A}
$$


$b)$ 

$$
\mathbf{x^T Ax}=\begin{bmatrix}x_1 & x_2 & \cdots & x_n\end{bmatrix}\begin{bmatrix} \displaystyle\sum_{i=1}^n a_{1i}x_i\\\  \displaystyle\sum_{i=1}^n a_{2i}x_i\\\ \vdots \\\  \displaystyle\sum_{i=1}^n a_{mi}x_i\end{bmatrix}
$$

Notice the issue with dimensionality here. For this product to exist, $m=n$ is a necessity. Now, we make this adjustment in our product to get:

$$
\begin{align*}
\mathbf{x^T Ax}=\langle\mathbf{x}, \mathbf{Ax}\rangle &= \sum_{i=1}^n\sum_{j=1}^n a_{ij}x_ix_j\\
&= \sum_{i=1}^n a_{ii}x_{i}^2 + \sum_{i=1}^n\sum_{\substack{j=1 \\ j\ne i}}^n a_{ij}x_ix_j
\end{align*}
$$

Which is a scalar. Therefore we have:

$$
\frac{\partial{\mathbf{x^TAx}}}{\partial{\mathbf{x}}}=\begin{bmatrix}\displaystyle\frac{\partial{\mathbf{x^T Ax}}}{\partial{x_1}} & \displaystyle\frac{\partial{\mathbf{x^T Ax}}}{\partial{x_2}} & \cdots & \displaystyle\frac{\partial{\mathbf{x^T Ax}}}{\partial{x_n}}\end{bmatrix}
$$

Finding the $k^{th}$ entry of the above vector:

$$
\begin{align*}
\frac{\partial \mathbf{x^T Ax}}{\partial x_k}&=\frac{\partial}{\partial x_k}\left(\sum_{i=1}^n a_{ii}x_{i}^2 + \sum_{i=1}^n\sum_{\substack{j=1 \\ j\ne i}}^n a_{ij}x_ix_j\right)\\
&=\frac{\partial}{\partial x_k}\left(\sum_{i=1}^n a_{ii}x_{i}^2\right) + \frac{\partial}{\partial x_k}\left(\sum_{i=1}^n\sum_{\substack{j=1 \\ j\ne i}}^n a_{ij}x_ix_j\right)\\
&= 2a_{kk}x_k + \sum_{\substack{j=1 \\ j\ne k}}^n a_{kj}x_j + \sum_{\substack{j=1 \\ j\ne k}}^n a_{jk}x_j\\
&= 2a_{kk}x_k + \sum_{\substack{j=1 \\ j\ne k}}^n (a_{kj} + a_{jk}) x_j\\
&= \sum_{j=1}^n (a_{kj} + a_{jk}) x_j\\
\end{align*}
$$

Writing the above in vector form:

$$
\begin{align*}
\frac{\partial{\mathbf{x^T Ax}}}{\partial{\mathbf{x}}}&=\begin{bmatrix}\displaystyle\frac{\partial{\mathbf{x^T Ax}}}{\partial{x_1}} & \displaystyle\frac{\partial{\mathbf{x^T Ax}}}{\partial{x_2}} & \cdots & \displaystyle\frac{\partial{\mathbf{x^T Ax}}}{\partial{x_n}}\end{bmatrix}\\
&= \begin{bmatrix}
 \displaystyle\sum_{j=1}^n (a_{1j} + a_{1k}) x_1\\
 \displaystyle\sum_{j=1}^n (a_{2j} + a_{2k}) x_2\\
\vdots\\
 \displaystyle\sum_{j=1}^n (a_{nj} + a_{nk}) x_n\\
\end{bmatrix}^T\\
&= \left(\begin{bmatrix}x_1\\\ x_2\\\ \vdots \\\ x_n\end{bmatrix}\begin{bmatrix}a_{11} + a_{11} & a_{12} + a_{21} & \cdots & a_{1n} + a_{n1} \\\ a_{21} + a_{12} & \cdots & \cdots & a_{2n} + a_{n2} \\\ \vdots & \vdots & \ddots & \vdots \\\ a_{n1} + a_{1n} & \cdots & \cdots & a_{nn} +a_{nn}\end{bmatrix}\right)^T
\end{align*}
$$


This is nothing but $\mathbf{x^T(A+A^T)}$.  Another form, $\mathbf{(A+A^T)x}$ is also often used. The difference in represntation indicates either the row or column form of the output. While solving an equation, however, we must be careful as to what format we are using and stay consistent with it throughout.

$c)$ Yes, this is possible. When $\mathbf{Ax=b}$ does not have a solution, we try to minimize the 2-norm $\lVert \mathbf{Ax-b} \rVert$. A slightly simpler calculation would be to minimize the square of this term. Thus, we try to minimize $\lVert \mathbf{Ax-b} \rVert^2$.

$$
\begin{align*}
\lVert \mathbf{Ax-b} \rVert^2&=\langle \mathbf{Ax-b} \rangle \langle \mathbf{Ax-b} \rangle \\
&=(\mathbf{Ax-b})^T(\mathbf{Ax-b})\\
&=(\mathbf{Ax})^T\mathbf{Ax}+(\mathbf{Ax})^T(-\mathbf{b})+(-\mathbf{b})^T(\mathbf{Ax})+(-\mathbf{b})^T(-\mathbf{b})\\
&=\mathbf{x}^T\mathbf{A}^T\mathbf{A}\mathbf{x}-\mathbf{x}^T\mathbf{A}^T\mathbf{b}-\mathbf{b}^T\mathbf{Ax}+\mathbf{b^T b}
\end{align*}
$$

Differentiating w.r.t $\mathbf{x}$, and equating to $0$, we get:

$$
\begin{align*}
&(\mathbf{A^T A+(A^T A)^T})\mathbf{x}-\mathbf{A^T b}-(\mathbf{b^T A})^T=0\\
\implies& \mathbf{x}=(\mathbf{A^T A})^{-1}\mathbf{A^T b}
\end{align*}
$$

The same result can also be obtained from the following differentiation:

$$
\begin{align*}
&\mathbf{x^T}(\mathbf{A^T A+(A^T A)^T})-(\mathbf{A^T b})^T-\mathbf{b^T A}=0\\
\implies &\mathbf{x^T}=\mathbf{b^T A}(\mathbf{A^T A})^{-1}\\
\implies &\mathbf{x}=(\mathbf{A^T A})^{-1}\mathbf{A^T b}
\end{align*}
$$


