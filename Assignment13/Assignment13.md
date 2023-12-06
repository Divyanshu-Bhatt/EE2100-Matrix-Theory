Matrix Theory: Assignment 13 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 13. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.


## Question 1
The induced norm of order $p$ of $\mathbf{A}\in\mathbb{R}^{n\times n}$ is defined as

$$
\lVert \mathbf{A} \rVert_p=\max_{\mathbf{x}\ne \mathbf{0}}\frac{\lVert\mathbf{A}\mathbf{x}\rVert _p}{\lVert \mathbf{x} \rVert _p}
$$

$a)$ Let $p = 1$

$$
\begin{align*}
\lVert \mathbf{A} \rVert_1&=\max_{\mathbf{x}\ne \mathbf{0}}\frac{\lVert\mathbf{A}\mathbf{x}\rVert_1}{\lVert \mathbf{x} \rVert_1} \\
\lVert\mathbf{A}\mathbf{x}\rVert_1 &= \sum_{i=1}^n \lvert\sum_{j=1}^n A_{ij}x_j \rvert \\
\implies \lVert\mathbf{A}\mathbf{x}\rVert_1 &\le \sum_{i=1}^n \sum_{j=1}^n \lvert A_{ij}x_j \rvert = \sum_{i=1}^n \sum_{j=1}^n \lvert A_{ij}\rvert \lvert x_j \rvert \\
\implies \lVert\mathbf{A}\mathbf{x}\rVert_1 &\le \sum_{j=1}^n \lvert x_j\rvert \sum_{i=1}^n \lvert A_{ij} \rvert \le \sum_{j=1}^n \lvert x_j\rvert\left( \max_{j} \sum_{i=1}^n \lvert A_{ij} \rvert\right)\\
\implies \lVert\mathbf{A}\mathbf{x}\rVert_1 &\le \left( \max_{j} \sum_{i=1}^n \lvert A_{ij} \rvert\right)\sum_{j=1}^n \lvert x_j\rvert = \left( \max_{j} \sum_{i=1}^n \lvert A_{ij} \rvert\right) \lVert \mathbf{x} \rVert_1\\
\implies \frac{\lVert\mathbf{A}\mathbf{x}\rVert_1}{\lVert \mathbf{x} \rVert_1} &\le \max_{j} \sum_{i=1}^n \lvert A_{ij} \rvert\\
\implies \lVert \mathbf{A} \rVert_1 &= \max_{j} \sum_{i=1}^n \lvert A_{ij} \rvert
\end{align*}
$$

This is the maximum sum of absolute values of elements in a column of $\mathbf{A}$.

Now, let $p = \infty$

$$
\begin{align*}
\lVert \mathbf{A} \rVert_\infty&=\max_{\mathbf{x}\ne \mathbf{0}}\frac{\lVert\mathbf{A}\mathbf{x}\rVert_\infty}{\lVert \mathbf{x} \rVert_\infty} \\
\lVert\mathbf{A}\mathbf{x}\rVert_\infty &= \max_{i}\left\lvert\sum_{j=1}^n A_{ij}x_j \right\rvert \\
\implies \lVert\mathbf{A}\mathbf{x}\rVert_\infty &\le \max_{i}\sum_{j=1}^n \lvert A_{ij}x_j \rvert = \max_{i}\sum_{j=1}^n \lvert A_{ij}\rvert \lvert x_j \rvert\\
\implies \lVert\mathbf{A}\mathbf{x}\rVert_\infty &\le  \max_{i}\sum_{j=1}^n \lvert A_{ij}\rvert \left(\max_{j}\lvert x_j \rvert\right) = \left(\max_{j}\lvert x_j \rvert\right)\max_{i}\sum_{j=1}^n \lvert A_{ij}\rvert \\
\implies \lVert\mathbf{A}\mathbf{x}\rVert_\infty &\le \lVert\mathbf{x}\rVert_\infty \left(\max_{i}\sum_{j=1}^n \lvert A_{ij}\rvert\right) \\
\implies \frac{\lVert\mathbf{A}\mathbf{x}\rVert_\infty}{\lVert \mathbf{x} \rVert_\infty} &\le \max_{i} \sum_{j=1}^n \lvert A_{ij} \rvert\\
\implies \lVert \mathbf{A} \rVert_\infty &= \max_{i} \sum_{j=1}^n \lvert A_{ij} \rvert
\end{align*}
$$

This is the maximum sum of absolute value of elements in a row of $\mathbf{A}$.

$b)$ Given $\lVert\mathbf{A}\rVert= \sigma _1$ and $\lVert \mathbf{b} \rVert = c$

$$
\begin{align*}
\lVert \mathbf{A} \rVert_2=\max_{\mathbf{b}\ne \mathbf{0}}\frac{\lVert\mathbf{A}\mathbf{b}\rVert _2}{\lVert \mathbf{b} \rVert _2} &= \sigma_1\\
\implies \frac{\lVert\mathbf{A}\mathbf{b}\rVert _2}{\lVert \mathbf{b} \rVert _2} &\le \sigma_1\\
\implies \frac{\lVert\mathbf{A}\mathbf{b}\rVert _2}{c} &\le \sigma_1\\
\implies \lVert\mathbf{A}\mathbf{b}\rVert _2 &\le \sigma_1 c
\end{align*}
$$

## Question 2
The frobenius norm is defined as

$$
\begin{align*}
\lVert \mathbf{A} \rVert_F &= \sqrt{\sum_i^m \sum_j^n \lvert a_{ij}\rvert^2} \\
\end{align*}
$$

Let $\mathbf{A} \in \mathbb{R}^{m \times n}$ and $\mathbf{B} \in \mathbb{R}^{n \times p}$

$$
\begin{align*}
\implies \lVert \mathbf{AB} \rVert_F &= \sqrt{\sum_i^m \sum_j^p \Big\lvert \sum_k^n a_{ik} b_{kj} \Big\rvert^2} \\
&\le \sqrt{\sum_i^m \sum_j^p \Big (\sum_k^n \lvert a_{ik} \rvert^2 \sum_k^n \lvert b_{kj} \rvert^2 \Big )} \\
&\le \sqrt{\sum_i^m \sum_j^p \Big ( \sum_{k, l}^n \lvert  a_{ik} \rvert^2 \lvert  b_{lj} \rvert^2 \Big )} \\
&\le \sqrt{\sum_i^m \sum_k^n  \lvert a_{ik} \rvert^2} \sqrt{\sum_l^n \sum_j^p \lvert b_{lj} \rvert^2} \\
&\le \lVert \mathbf{A} \rVert _F \lVert \mathbf{B} \rVert _F
\end{align*}
$$

<p align='right'>$\square$</p>

## Question 3
Let $\mathbf{C}$ such that $\mathbf{C} = \mathbf{AB}$, and $\mathbf{C_j}$ denote the $j^{th}$ column of $\mathbf{C}$.

Then, we have:

$$
\begin{align*}
\mathbf{\lVert C \rVert_F}^2 &=  \sum_{j} \lVert \mathbf{C_j} \rVert_2^2\\
&= \sum_{j} \lVert \mathbf{AB_j} \rVert_2^2  \\
\end{align*}
$$

We define the L2 norm of a matrix as:

$$
\begin{align*}
&\lVert \mathbf{A} \rVert_2 = \max_{\mathbf{x}\ne \mathbf{0}}\frac{\lVert\mathbf{A}\mathbf{x}\rVert_2}{\lVert \mathbf{x} \rVert_2}\\
\implies & \lVert \mathbf{A}\rVert_2 \lVert\mathbf{x}\rVert_2  \le \lVert \mathbf{A}\mathbf{x}\rVert_2   \qquad \forall \mathbf{x} \in \mathbb{R}^n
\end{align*}
$$

Using the above inequality we can say that $\lVert \mathbf{AB_j} \rVert_2 \leq \lVert \mathbf{A} \rVert_2 \lVert \mathbf{B_j} \rVert_2$.

$$
\begin{align*}
\mathbf{\lVert C \rVert_F}^2  &\leq \sum_{j}\lVert \mathbf{A} \rVert_2^2 \lVert \mathbf{B_j} \rVert^2 \\
&\leq \lVert \mathbf{A} \rVert_2^2 \sum_{j} \lVert \mathbf{B_j} \rVert^2 \\
&\leq \lVert\mathbf{A}\rVert_2^2 \lVert\mathbf{B}\rVert_F^2
\end{align*}
$$

<p align='right'>$\square$</p> 

## Question 4
$a)$ Consider the matrix $\mathbf{A}$, such that

$$
\mathbf{A}=\begin{bmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{bmatrix}
$$

Thus, we have 

$$
\mathbf{A^{-1}}={1 \over (a_{11}a_{22}-a_{12}a_{21})}\begin{bmatrix}
a_{22} & -a_{12} \\
-a_{21} & a_{11}
\end{bmatrix}
$$

Let's now find the infinity norms:

$$
\lVert \mathbf{A} \rVert_\infty=\max\{\lvert a_{11} \rvert+\lvert a_{12}\rvert,\lvert a_{21} \rvert+\lvert a_{22}\rvert\}
$$

$$
\lVert \mathbf{A} \rVert_\infty=\max\{{1 \over (a_{11}a_{22}-a_{12}a_{21})}(\lvert a_{22} \rvert+\lvert -a_{12}\rvert),{1 \over (a_{11}a_{22}-a_{12}a_{21})}(\lvert -a_{21} \rvert+\lvert a_{11}\rvert)\}
$$

$$
\implies \kappa(\mathbf{A})={1 \over (a_{11}a_{22}-a_{12}a_{21})}\max\{\lvert a_{11} \rvert+\lvert a_{12}\rvert,\lvert a_{21} \rvert+\lvert a_{22}\rvert\}\max\{(\lvert a_{22} \rvert+\lvert -a_{12}\rvert),(\lvert -a_{21} \rvert+\lvert a_{11}\rvert)\}
$$

The condition number is large when the determinant is close to 0. That is, the matrix is ill conditioned when it is closer to being singular.

$b)$ The condition number for singular matrices is $\infty$. Note for singular matrices $\mathbf{A^{-1}}$ does not exist.

$c)$ Given 

$$
\mathbf{A}=\begin{bmatrix}
2 & 3 \\
3.3 & 5
\end{bmatrix}
$$

$$
\mathbf{A^{-1}}={1 \over (10-9.9)}\begin{bmatrix}
5 & -3 \\
-3.3 & 2
\end{bmatrix}
$$

$$
\mathbf{A^{-1}}=\begin{bmatrix}
50 & -30 \\
-33 & 20
\end{bmatrix}
$$

Thus, 

$$
\lVert \mathbf{A} \rVert_\infty=8.3
$$
$$
\lVert \mathbf{A^{-1}} \rVert_\infty=80
$$

Therefore,

$$
\kappa(\mathbf{A})=8.3 \times 80=664
$$

$d)$

$$
\mathbf{x}=\mathbf{A^{-1}b}=\begin{bmatrix}1 \\\ 1\end{bmatrix}
$$

Now, solving for the perturbed vector $\mathbf{b}$, we get:

$$
\mathbf{x'}=\mathbf{A^{-1}b'}=\begin{bmatrix}3 \\\ -0.3\end{bmatrix}
$$

The large deviation despite a small change in $\mathbf{b}$ is due to the large condition number.
