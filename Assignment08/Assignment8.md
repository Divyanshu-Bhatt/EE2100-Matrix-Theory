Matrix Theory: Assignment 8 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 8. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.


## Question 2

Let $T$ be the transformation corresponding to the reflection of a vector about a given vector $\mathbf{u}$, and $\mathbf A$ be the corresponding transformation matrix. 

$$
\mathbf A = 
\begin{bmatrix}
T(e_1) & T(e_2) & \cdots & T(e_n)
\end{bmatrix}
$$

where $\mathbf{e_1}, \mathbf{e_2}\cdots\mathbf{e_n}$ represent the orthogonal basis vectors.

Also, we know that the reflection of a vector along a given vector $\mathbf{u}$ can be given as:

$$
\begin{align*}
\mathbf T(\mathbf e_i) &= 2\frac{\left\langle\mathbf{e_i} , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2^2}\mathbf{u} - \mathbf{e_i} \\
\mathbf{y_i} &= 2\frac{\left\langle\mathbf{e_i} , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2^2}\mathbf{u} - \mathbf{e_i}
\end{align*}
$$

On substituting these values in $\mathbf A$, we get:

$$
\begin{align*}
\mathbf A &= 
\begin{bmatrix}
y_1 & y_2 & \cdots & y_n
\end{bmatrix} \\
\mathbf A^T &= 
\begin{bmatrix}
y_1 \\
y_2 \\
\vdots \\
y_n
\end{bmatrix} \\
\implies 
\mathbf A\mathbf A^T &= 
\begin{bmatrix}
\left\langle\mathbf{y_1} , \mathbf{y_1} \right\rangle &
\left\langle\mathbf{y_1} , \mathbf{y_2} \right\rangle &
\cdots &
\left\langle\mathbf{y_1} , \mathbf{y_n} \right\rangle \\
\vdots &\vdots &\ddots & \vdots\\
\left\langle\mathbf{y_n} , \mathbf{y_1} \right\rangle &
\left\langle\mathbf{y_n} , \mathbf{y_2} \right\rangle &
\cdots&
\left\langle\mathbf{y_n} , \mathbf{y_n} \right\rangle \\
\end{bmatrix}
\end{align*}
$$

For any two integers $i$ and $j$, $0 \leq i,j\leq n$

$$
\begin{align*}
\left\langle\mathbf{y}_i, \mathbf{y}_j \right\rangle &= \left\langle\mathbf{2\frac{\left\langle\mathbf{e}_i , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2^2}\mathbf{u} - \mathbf{e}_i}, \mathbf{2\frac{\left\langle\mathbf{e}_j , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2^2}\mathbf{u} - \mathbf{e}_j} \right\rangle\\
&= 4 \left(\frac{\left\langle\mathbf{e}_i, \mathbf{u}\right\rangle}{\lVert \mathbf{u} \rVert_2^2}\frac{\left\langle\mathbf{e})j,\mathbf{u}\right\rangle}{\lVert\mathbf{u} \rVert_2^2}\right)\left\langle\mathbf{u},\mathbf{u}\right\rangle -2\frac{\left\langle\mathbf{e}_i , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2^2} \left\langle\mathbf{e}_j, \mathbf{u}\right\rangle -2\frac{\left\langle\mathbf{e}_j, \mathbf{u}\right\rangle}{\lVert\mathbf{u}\rVert_2^2}\left\langle\mathbf{e}_i, \mathbf{u}\right\rangle + \left\langle\mathbf{e}_i, \mathbf{e}_j\right\rangle\\
&=4\left(\frac{\left\langle\mathbf{e}_i, \mathbf{u}\right\rangle}{\lVert \mathbf{u}\rVert_2^2}\frac{\left\langle\mathbf{e}_j, \mathbf{u}\right\rangle}{\lVert\mathbf{u} \rVert_2^2}\right)\lVert\mathbf{u}\rVert_2^2 -2\frac{\left\langle\mathbf{e}_i , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2^2} \left\langle\mathbf{e}_j , \mathbf{u} \right\rangle -2\frac{\left\langle\mathbf{e}_j , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2^2} \left\langle\mathbf{e}_i , \mathbf{u} \right\rangle + \left\langle\mathbf{e}_i , \mathbf{e}_j \right\rangle \\
\end{align*}
$$

$$
\begin{align*}
&= 4 \left(\frac{\left\langle\mathbf{e}_i , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2} \frac{\left\langle\mathbf{e}_j , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2}\right) -2\frac{\left\langle\mathbf{e}_j , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2^2} \left\langle\mathbf{e}_i, \mathbf{u} \right\rangle-2\frac{\left\langle\mathbf{e}_i, \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2^2} \left\langle\mathbf{e}_j , \mathbf{u} \right\rangle + \left\langle\mathbf{e}_i , \mathbf{e}_j \right\rangle \\
&= 4\left(\frac{\left\langle\mathbf{e}_i, \mathbf{u}\right\rangle}{\lVert \mathbf{u} \rVert_2}\frac{\left\langle\mathbf{e}_j, \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2} \right) - 4 \frac{\left\langle\mathbf{e}_i , \mathbf{u} \right\rangle \left\langle\mathbf{e}_j , \mathbf{u} \right\rangle}{\lVert \mathbf{u} \rVert_2^2} + \left\langle\mathbf{e}_i , \mathbf{e}_j \right\rangle \\
&=  \left\langle\mathbf{e}_i , \mathbf{e}_j \right\rangle
\end{align*}
$$

When $i=j$,

$$
\begin{align*}
\left\langle\mathbf{y_i} , \mathbf{y_j} \right\rangle &= 
\left\langle\mathbf{y_i} , \mathbf{y_i} \right\rangle \\
&= \left\langle\mathbf{e_i} , \mathbf{e_i} \right\rangle  \\
&= \lVert \mathbf{e_i} \rVert_2^2 \\
&= 1
\end{align*}
$$

Now, when $i \neq j$,

$$
\begin{align*}
\left\langle\mathbf{y_i} , \mathbf{y_j} \right\rangle &= 
\left\langle\mathbf{e_i} , \mathbf{e_j} \right\rangle  \\
&= 0
\end{align*}
$$

Hence, 

$$
\left\langle\mathbf{y_i} , \mathbf{y_j} \right\rangle = 
\begin{cases}
1, &\text{if } i=j \\
0, &\text{otherwise}
\end{cases}
$$

$$
\begin{gather*}
\mathbf A\mathbf A^T=
\begin{bmatrix}
1 & 0 & \cdots & 0 \\
0 & 1 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots\\
0 & 0 & \cdots & 1\\
\end{bmatrix}\\\
\mathbf A\mathbf A^T = I
\end{gather*}
$$

Thus, we have proved that the transformation matrix is orthogonal.
Subsequently,

$$
\mathbf A^{-1} = \mathbf A^T
$$


## Question 3
$\underline{\textbf{NOTE:}}$ Computing the inverse using an augmented matrix is another valid method which has been covered in Tutorial 8 Part C.

Given that

$$
\mathbf A = \begin{bmatrix}
1 & 2 & 3 & 4 \\
3 & 2 & 1 & 1 \\
2 & 1 & 3 & 5 \\
4 & 3 & 2 & 1 \\
\end{bmatrix}
$$

We will compute the inverse by using $\mathbf {LU}$ decomposition on $\mathbf A$.

$$
\mathbf {A = LU } \\
\implies \mathbf{A^{-1} = U^{-1} L^{-1}}
$$

where

$$
\begin{align*}
\left(\mathbf{L} _ p \right) _ {i,i} &= 
    \begin{cases}
        1 & i \in \{1,2, \cdots, p\}\\
        \left(\mathbf{A} _ {p-1} \right) _ {p,p} & i \in \{p+1,p+2, \cdots ,n \}\\
    \end{cases}\\
\left(\mathbf{L} _ p\right) _ {i,j} &= 
    \begin{cases}
        -\left(\mathbf{A} _ {p-1}\right) _ {i,j} & j = p \ \text{and} \  i > j\\
        0 & \text{otherwise}\\
    \end{cases}
\end{align*} 
$$

$$
\begin{align*}
\implies \mathbf{L}_1 &= 
\begin{bmatrix}
1 & 0 & 0 & 0 \\
-3 & 1 & 0 & 0 \\
-2 & 0 & 1 & 0 \\
-4 & 0 & 0 & 1 \\
\end{bmatrix} \\
\implies \mathbf{A}_1 &= \mathbf{L}_1\mathbf{A} = \begin{bmatrix} 
1 & 2 & 3 & 4 \\
0 & -4 & -8 & -11 \\
0 & -3 & -3 & -3 \\
0 & -5 & -10 & -15 \\
\end{bmatrix} \\
\implies \mathbf{L}_2 &= 
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0\\
0 & -3/4 & 1 & 0 \\
0 & -5/4 & 0 & 1 \\
\end{bmatrix} \\
\implies \mathbf{A}_2 &= \mathbf{L}_2\mathbf{A}_1 = 
\begin{bmatrix}
1 & 2 & 3 & 4 \\
0 & -4 & -8 & -11 \\
0 & 0 & 3 & 21/4 \\
0 & 0 & 0 & -5/4 \\
\end{bmatrix} \\
\end{align*}
$$

Since $\mathbf{A_{2}}$ is a complete lower traingular matrix, there is no need to compute $\mathbf{L_3} . (\mathbf{L_3 = \mathbf{I}})$


$$
\begin{align*}
\implies \mathbf{U} &= \mathbf{A}_2 = \mathbf{L}_2\mathbf{L}_1\mathbf{A} = \mathbf{L}^{-1} \mathbf{A}\\
\implies \mathbf{U} &= 
\begin{bmatrix}
1 & 2 & 3 & 4 \\
0 & -4 & -8 & -11 \\
0 & 0 & 3 & 21/4 \\
0 & 0 & 0 & -5/4 \\
\end{bmatrix}
\end{align*}
$$

$$
\mathbf{L}^{-1} = \mathbf{L}_2\mathbf{L}_1  = \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0\\
0 & -3/4 & 1 & 0 \\
0 & -5/4 & 0 & 1 \\
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 & 0 \\
-3 & 1 & 0 & 0 \\
-2 & 0 & 1 & 0 \\
-4 & 0 & 0 & 1 \\
\end{bmatrix}\\ 
$$

$$
\implies \mathbf{L}^{-1} = 
\begin{bmatrix} 
1 & 0 & 0 & 0 \\
-3 & 1 & 0 & 0 \\
1/4 & -3/4 & 1 & 0 \\
-1/4 & -5/4 & 0 & 1 \\
\end{bmatrix}
$$

We can calculate the inverse of the upper triangular matrix $\mathbf U$ using the property that the inverse of an upper triangular matrix is also an upper triangular matrix (the same holds for lower triangular matrices too). This gives us

$$
\mathbf{U}^{-1}\mathbf{U} = \begin{bmatrix}u_{11} & u_{12} & u_{13} & u_{14} \\
0 & u_{22} & u_{23} & u_{24}\\
0 & 0 & u_{33} & u_{34} \\
0 & 0 & 0 & u_{44} \\
\end{bmatrix}\begin{bmatrix}
1 & 2 & 3 & 4 \\
0 & -4 & -8 & -11 \\
0 & 0 & 3 & 21/4 \\
0 & 0 & 0 & -5/4 \\
\end{bmatrix} = 
\begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end{bmatrix} 
$$

On comparing equations on both sides and solving, we get

$$
\begin{align*}
\mathbf{U}^{-1} &= 
\begin{bmatrix} 
1 & 1/2 & 1/3 & 1/5 \\
0 & -1/4 & -2/3 & -3/5 \\
0 & 0 & 1/3 & 7/5 \\
0 & 0 & 0 & -4/5 \\
\end{bmatrix} \\
\implies \mathbf{A}^{-1} &= \mathbf{U}^{-1}\mathbf{L}^{-1} = 
\begin{bmatrix} 
1 & 1/2 & 1/3 & 1/5 \\
0 & -1/4 & -2/3 & -3/5 \\
0 & 0 & 1/3 & 7/5 \\
0 & 0 & 0 & -4/5 \\
\end{bmatrix}
\begin{bmatrix} 
1 & 0 & 0 & 0 \\
-3 & 1 & 0 & 0 \\
0.25 & -0.75 & 1 & 0 \\
-0.25 & -1.25 & 0 & 1 \\
\end{bmatrix} \\
\implies \mathbf{A}^{-1} &= \begin{bmatrix} 
-7/15 & 0 & 1/3 & 1/5 \\
11/15 & 1 & -2/3 & -3/5 \\
-4/15 & -2 & 1/3 & 7/5 \\
1/5 & 1 & 0 & -4/5 \\
\end{bmatrix}
\end{align*}
$$

## Question 4

The basis of the subspace is $\set{\mathbf{e}_1 − \mathbf{e}_2, \mathbf{e}_1 + \mathbf{e}_2}$. The projection of $\mathbf{x}$ onto this subspace is given by

$$
\begin{align*}
\mathrm{Proj}_{\mathbf{x}} &= \frac{\left\langle\mathbf{x}  ,\mathbf{e}_1 − \mathbf{e}_2\right\rangle}{\left\langle\mathbf{e}_1 − \mathbf{e}_2, \mathbf{e}_1 − \mathbf{e}_2\right \rangle}\left(\mathbf{e}_1 − \mathbf{e}_2\right) + \frac{\left\langle\mathbf{x} , \mathbf{e}_1 + \mathbf{e}_2\right\rangle}{\left\langle\mathbf{e}_1 + \mathbf{e}_2 , \mathbf{e}_1 + \mathbf{e}_2\right\rangle}(\mathbf{e}_1 + \mathbf{e}_2) \\
&= \frac{\left\langle\mathbf{x} , \mathbf{e}_1 − \mathbf{e}_2\right\rangle}{2}(\mathbf{e}_1 − \mathbf{e}_2) + \frac{\left\langle\mathbf{x}, \mathbf{e}_1 + \mathbf{e}_2\right\rangle}{2}(\mathbf{e}_1 + \mathbf{e}_2) \\
&= \frac{1}{2}\left(\left\langle\mathbf{x} , \mathbf{e}_1\right\rangle − \left\langle\mathbf{x}, \mathbf{e}_2\right\rangle\right)(\mathbf{e}_1 − \mathbf{e}_2) + \frac{1}{2}\left(\left\langle\mathbf{x}, \mathbf{e}_1\right\rangle + \left\langle\mathbf{x}, \mathbf{e}_2\right\rangle\right)(\mathbf{e}_1 + \mathbf{e}_2) \\
&= \left\langle\mathbf{x}, \mathbf{e}_1\right\rangle \mathbf{e}_1 + \left\langle\mathbf{x} \cdot \mathbf{e}_2\right\rangle \mathbf{e}_2 \\
\end{align*}
$$

The matrix $\mathbf{A}$ is given by

$$
\mathbf{A} = \begin{bmatrix} 1&0&0 \\\ 0&1&0 \\\ 0&0&0 \end{bmatrix}
$$

We can verify whether $\mathbf{A}^2 = \mathbf{I}$ by computing $\mathbf{A}^2$

$$
\begin{align*}
\mathbf{A}^2 &= \begin{bmatrix} 1&0&0 \\\ 0&1&0 \\\ 0&0&0 \end{bmatrix} \begin{bmatrix} 1&0&0 \\\ 0&1&0 \\\ 0&0&0 \end{bmatrix} \\
&= \begin{bmatrix} 1&0&0 \\\ 0&1&0 \\\ 0&0&0 \end{bmatrix} \\
&\neq \mathbf{I}
\end{align*}
$$
