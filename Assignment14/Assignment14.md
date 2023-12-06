Matrix Theory: Assignment 14 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 14. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.

## Question 1
Finding the singular values of $\mathbf{A}$ by computing the eigenvalues of $\mathbf{A}^T\mathbf{A}$

$$
\begin{align*}
\mathbf{A^T A} &= \begin{bmatrix}1 & 0 & 0 \\\10 & 10 & 0\\\11 & 1 & 10 \end{bmatrix} 
\begin{bmatrix}
1 & 10 & 11 \\
0 & 10 & 1 \\
0 & 0 & 10  \\
\end{bmatrix}=
\begin{bmatrix}
1 & 10 & 11 \\
10 & 200 & 120 \\
11 & 120 & 222  \\
\end{bmatrix}
\end{align*}
$$

$$
\begin{align*}
\lvert \mathbf{A^TA} - \lambda \mathbf{I} \rvert &=  
\begin{vmatrix}
1 - \lambda & 10 & 11 \\
10 & 200 - \lambda & 120 \\
11 & 120 & 222 - \lambda \\
\end{vmatrix} \\
\implies \lambda &= 332.17, 90.50, 0.33
\end{align*}
$$

Thus, the largest and smallest singular values of the matrix are $\sigma_1 = \sqrt{332.17}$ and $\sigma_3 =\sqrt{0.33}$ 

$$
\kappa(\mathbf{A})= \sqrt{332.17\over 0.33} \approx 31.73
$$

Similarly for $\mathbf{B}$

$$
\begin{align*}
\mathbf{B^T B} &= 
\begin{bmatrix}
2 & 0 & 0 \\
20 & 20 & 0 \\
22 & 2 & 20  \\
\end{bmatrix} 
\begin{bmatrix}
2 & 20 & 22 \\
0 & 20 & 2 \\
0 & 0 & 20  \\
\end{bmatrix}=
\begin{bmatrix}
4 & 40 & 44 \\
40 & 800 & 480 \\
44 & 480 & 888  \\
\end{bmatrix}
\end{align*}
$$

$$
\begin{align*}
\lvert \mathbf{B^T B} - \lambda \mathbf{I} \rvert &=  
\begin{vmatrix}
4 - \lambda & 40 & 44 \\
40 & 800 - \lambda & 480 \\
44 & 480 & 888 - \lambda \\
\end{vmatrix} \\
\implies \lambda &= 1328.68, 361.99, 1.33
\end{align*}
$$

Thus, the largest and smallest singular values of the matrix are $\sigma_1 = \sqrt{1328.68}$ and $\sigma_3 = \sqrt{1.33} $ 

$$
\kappa(\mathbf{B})= \sqrt{1328.68\over 1.33} \approx 31.73
$$


Note that $\mathbf{B} = 2\mathbf{A}$ and the eigenvalues of $\mathbf{B}$ are 4 times the eigenvalues of $\mathbf{A}$.

Thus we can conclude that $\kappa(\mathbf{\alpha A}) = \kappa(\mathbf{A})$ but under the added constraint of $\alpha \in \mathbb{R} \backslash \set{0}$

## Question 2
The transformation matrix $\mathbf{A}$ corresponding to the rotation of a vector $\mathbf{x}$ by an angle $\theta$ is given by 

$$
\begin{align*}
\mathbf{A} &= \begin{bmatrix}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta
\end{bmatrix}
\end{align*}
$$

Computing the singular values of $\mathbf{A}$ by computing the eigenvalues of $\mathbf{A}^T\mathbf{A}$

$$
\begin{align*}
\mathbf{A}^T\mathbf{A} &= \begin{bmatrix}
\cos \theta & \sin \theta \\
-\sin \theta & \cos \theta
\end{bmatrix} \begin{bmatrix}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta
\end{bmatrix} \\
&= \begin{bmatrix}
\cos^2 \theta + \sin^2 \theta & -\cos \theta \sin \theta + \sin \theta \cos \theta \\
-\sin \theta \cos \theta + \cos \theta \sin \theta & \sin^2 \theta + \cos^2 \theta
\end{bmatrix} \\
&= \begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}
\end{align*}
$$

The eigenvalues of $\mathbf{A}^T\mathbf{A}$ are $\lambda_1 = 1$ and $\lambda_2 = 1$. Thus, the singular values of $\mathbf{A}$ are $\sigma_1 = 1$ and $\sigma_2 = 1$.

Thus, the condition number of $\mathbf{A}$ is given by

$$
\begin{align*}
\kappa(\mathbf{A}) &= {\lvert \sigma_1 \rvert \over \lvert \sigma_2 \rvert} = {1 \over 1} = 1
\end{align*}
$$


## Question 3
Finding the transformation matrix $\mathbf{A}$ corresponding to the reflection of a vector $\mathbf{x}$ about a given vector $\mathbf{v}$.

Let $\theta$ be the angle between $\mathbf{x}$ and $\mathbf{v}$ given by $\theta = \cos^{-1} \left( {\langle \mathbf{x}, \mathbf{v}\rangle \over \lVert \mathbf{x} \rVert \lVert \mathbf{v} \rVert} \right)$. 

For reflection about $\mathbf{v}$, we need to rotate $\mathbf{x}$ by $2\theta$. Thus, the transformation matrix $\mathbf{A}$ is given by

$$
\begin{align*}
\mathbf{A} &= \begin{bmatrix}
\cos 2\theta & -\sin 2\theta \\
\sin 2\theta & \cos 2\theta
\end{bmatrix} \\
\end{align*}
$$

As we calculated in the previous question the singular values of the above matrix are $\sigma_1 = 1$ and $\sigma_2 = 1$ (as they don't depend on $\theta$) Thus, the condition number of $\mathbf{A}$ is given by

$$
\begin{align*}
\kappa(\mathbf{A}) &= {\lvert \sigma_1 \rvert \over \lvert \sigma_2 \rvert} = {1 \over 1} = 1
\end{align*}
$$

