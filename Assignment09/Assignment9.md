Matrix Theory: Assignment 9 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 9. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.

## Question 2
To prove:

$$
\mathbf{A}^2 =  \mathrm{tr}{\mathbf{(A)}}\mathbf{A} - \det{\mathbf{(A)}}\mathbf{I}
$$

where $\mathrm{tr}(\mathbf{A})$ is the trace of a matrix and $\mathrm{det}(\mathbf{A})$ is the determinant of a matrix, the simplest method would be the brute force comparison. Consider $\mathbf{A}$ as follows:

$$
\mathbf{A} = \begin{bmatrix} a_{11} & a_{12} \\\ a_{21} & a_{22} \end{bmatrix} 
$$

Now consider the RHS of the equation

$$
\begin{align*}
\mathrm{tr}(\mathbf{A}) &= a_{11} + a_{22} \\
\end{align*}
$$

$$
\begin{align*}
\det(\mathbf{A}) &= a_{11}a_{22} - a_{12}a_{21} \\
\end{align*}
$$

$$
\begin{align*}
\mathrm{tr}(\mathbf{A})\mathbf{A} - \det(\mathbf{A})\mathbf{I} &= (a_{11}+a_{22})\begin{bmatrix} a_{11} & a_{12} \\\ a_{21} & a_{22} \end{bmatrix} - (a_{11}a_{22} - a_{12}a_{21})\begin{bmatrix} 1 & 0 \\\ 0 & 1 \end{bmatrix} \\
&= \begin{bmatrix} a_{11}^2 + a_{11}a_{22} & a_{11}a_{12} + a_{22}a_{12} \\\ a_{11}a_{21} + a_{22}a_{21} & a_{11}a_{22} + a_{22}^2 \end{bmatrix} - \begin{bmatrix} a_{11}a_{22} - a_{12}a_{21} & 0 \\\ 0 & a_{11}a_{22} - a_{12}a_{21} \end{bmatrix} \\
&=  \begin{bmatrix} a_{11}^2 + a_{12}a_{21} & a_{11}a_{12} + a_{22}a_{12} \\\ a_{11}a_{21} + a_{22}a_{21} & a_{12}a_{21} + a_{22}^2 \end{bmatrix}\\
&=  \begin{bmatrix} a_{11}a_{11} + a_{12}a_{21} & a_{11}a_{12} + a_{12}a_{22} \\\ a_{21}a_{11} + a_{22}a_{21} & a_{21}a_{12} + a_{22}a_{22} \end{bmatrix}\\
&=  \begin{bmatrix} a_{11} & a_{12} \\\ a_{21} & a_{22} \end{bmatrix}\begin{bmatrix} a_{11} & a_{12} \\\ a_{21} & a_{22} \end{bmatrix} \\
&= \mathbf{A}\mathbf{A}\\
&= \mathbf{A}^2
\end{align*}
$$

<p align='right'>$\square$</p>

## Question 3
Using the result obtained in Question 2, we have:

$$
\begin{align*}
(\mathbf{AB-BA})^2&=(\mathbf{AB-BA})\mathrm{tr}(\mathbf{AB-BA})-\det(\mathbf{AB-BA})\mathbf I\\ 
&= -\det(\mathbf{AB-BA})\mathbf I
\end{align*}
$$

where $\mathbf I$ is the identity matrix. Taking trace on both sides we get:

$$
\begin{align*}
\mathrm{tr}\left((\mathbf{AB-BA})^2\right)&=\mathrm{tr}\left(-\det(\mathbf{AB-BA})\mathbf I\right)\\
&=-2\det(\mathbf{AB-BA})
\end{align*}
$$

Now, 

$$
\begin{align*}
\mathrm{tr}\left((\mathbf{AB-BA})^2\right)&=\mathrm{tr}\left((\mathbf{AB-BA})(\mathbf{AB-BA})\right)\\
&=\mathrm{tr}(\mathbf{ABAB}-\mathbf{AB^2A}-\mathbf{BA^2B}+\mathbf{BABA})
\end{align*}
$$

Now, $\mathrm{tr}(\mathbf{ABAB})=\mathrm{tr}(\mathbf{BABA})$ from the property $\mathrm{tr}(\mathbf{XY})=\mathrm{tr}(\mathbf{YX})$ and similarly using the same property we can say

$$
\begin{align*}
\mathrm{tr}(\mathbf{ABBA})&=\mathrm{tr}(\mathbf{ABAB})=\mathrm{tr}(\mathbf{AABB})
\end{align*}
$$

Using the above equations in the original equation we get

$$
\begin{align*}
\mathrm{tr}((\mathbf{AB-BA})^2)&=2\mathrm{tr}(\mathbf{ABAB}-\mathbf{AABB})\\
&=-2\det(\mathbf{AB-BA})\\
\implies \mathrm{tr}(\mathbf{ABAB}-\mathbf{AABB})&=-\det(\mathbf{AB-BA})
\end{align*}
$$

As both terms are equal we can say that

$$
P\set{\mathrm{tr}\left(\mathbf{ABAB}\right) > \mathrm{tr}\left(\mathbf{A^2B^2}\right)}= P\set{\det\left(\mathbf AB - \mathbf BA\right) < 0}
$$

<p align='right'>$\square$</p>

## Question 4
We want to prove that the determinant of an upper traingular matrix is the product of its diagonal entries.

We know that in an upper triangular matrix, all the entries below the diagonal are zero. Thus, for a $n\times n$ upper triangular matrix, it will be of the form:

$$
\mathbf A = \begin{bmatrix}
a_{11} & a_{12} & \cdots & a_{1n}\\ 
0 & a_{22} &  \cdots & \vdots  \\
\vdots &\vdots & \ddots & a_{(n-1)n} \\
0 & 0 & \cdots & a_{nn}\\
\end{bmatrix}
$$

As all the terms in the first column are zero except the first one, the determinant of the matrix can be written as:

$$
\det(\mathbf A) = a_{11}\times \det(\mathbf B) \\
$$


$$ \text{where } \mathbf B=
\begin{bmatrix}
a_{22} & a_{23} & \cdots & a_{2n}\\ 
0 & a_{33} & \cdots &  \vdots \\
\vdots &\vdots & \ddots & a_{(n-1)n} \\
0 & 0 &\cdots & a_{nn}\\
\end{bmatrix}
$$

Similarly, we can write $\det(\mathbf B)$ as:

$$
\det(\mathbf B) = a_{22}\times \det(\mathbf C) \\
$$

$$ \text{where } \mathbf C=
\begin{bmatrix}
a_{33} & a_{34} & \dots & a_{3n}\\ 
0 & a_{44} & \cdots &  \vdots \\
\vdots &\vdots & \ddots & a_{(n-1)n} \\
0 & 0 & \cdots  & a_{nn}\\
\end{bmatrix}
$$

We can continue this process until we arrive at a matrix of dimensions $1\times 1$, whose determinant would be the value of the entry i.e. $a_{nn}$

Thus, we can see that:

$$
\det(\mathbf A)=a_{11}\times a_{22} \dots \times a_{nn}
$$
