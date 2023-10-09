Matrix Theory: Assignment 6 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 6. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.

## Question 2

The null space of a matrix $\mathbf{A} \in \mathbb{R}^{m \times n}$ is defined as 

$$
\mathcal{N}(\mathbf{A}) := \set{\mathbf{x} \in \mathbb{R}^n | \mathbf{Ax}=0}
$$

The left null space of a matrix $\mathbf{A} \in \mathbf{R}^{m \times n}$ is defined as 

$$
\mathcal{N}(\mathbf{A^T}):=\{\mathbf{x} \in \mathbb{R}^m | \mathbf{A^{T}x}=0\}
$$ 

Let $\mathbf{A}$ be defined using column vectors as follows.

$$
\mathbf{A}=[\mathbf{a_1},\mathbf{a_2}, \cdots \mathbf{a_n}]
$$

Any vector $\mathbf{y}$ in the column space of $\mathbf{A}$ can be expressed as 

$$
\mathbf{y}=c_1\mathbf{a_1}+c_2\mathbf{a_2}+\cdots+c_n\mathbf{a_n}
$$

$$
\mathbf{A}=\begin{bmatrix}
			a_{11}  & a_{12}  & \cdots & a_{1n} \\
			a_{21}  & a_{22}  & \cdots & a_{2n} \\  
			\vdots & \vdots &\cdots & \vdots \\
			a_{m1}  & a_{m2}  & \cdots & a_{mn} \\
			\end{bmatrix}
$$


$$
\begin{align*}
\mathbf{A^T}\mathbf{x} &=\begin{bmatrix}
			a_{11}  & a_{21}  & \cdots & a_{m1} \\
			a_{12}  & a_{22}  & \cdots & a_{m2} \\  
			\vdots & \vdots &\cdots & \vdots \\
			a_{1n}  & a_{2n}  & \cdots & a_{mn} \\
			\end{bmatrix}
            \begin{bmatrix}
			x_{1} \\
			x_{2}  \\  
			\vdots  \\
			x_{m}  \\
			\end{bmatrix}\\
            &=\begin{bmatrix}
			(a_{11}x_1+a_{21}x_2 +\cdots + a_{m1}x_m )  \\
			(a_{12}x_1+a_{22}x_2 +\cdots + a_{m2}x_m ) \\  
			\vdots \\
			(a_{1n}x_1+a_{2n}x_2 +\cdots + a_{mn}x_m ) \\
			\end{bmatrix}\\
            &=\begin{bmatrix}
			0&
			0&
			\cdots  &
			0 
			\end{bmatrix}^T
            \end{align*}
$$

Therefore, we have 

$$
\begin{align*}
\mathbf{a_1}^T\mathbf{x}&=0, \\\
\mathbf{a_2}^T\mathbf{x}&=0 \\\
&\vdots \\\
\mathbf{a_n}^T\mathbf{x}&=0
\end{align*}
$$

Now, 

$$
\mathbf{y}^T\mathbf{x}=(c_1\mathbf{a_1}+c_2\mathbf{a_2}+\cdots+c_n\mathbf{a_n})^T\mathbf{x}=(c_1\mathbf{a_1}^T\mathbf{x}+c_2\mathbf{a_2}^T\mathbf{x}+\cdots+c_n\mathbf{a_n}^T\mathbf{x})=0
$$

But,  

$$
\mathbf{y}^T\mathbf{x}=\mathbf{y} \cdot \mathbf{x}=0
$$

This is nothing but the dot product of any vector $\mathbf{y}$ lying in the column space of $\mathbf{A}$ and any vector $\mathbf{x}$ lying in the left null space of $\mathbf{A}$. Since the dot product is 0 for any pair of such vectors $\mathbf{y},\mathbf{x}$, the column space of a matrix is orthogonal to its left null space. 

<p align='right'>$\square$</p>

## Question 3

We consider the system of linear equations given by:

$$
\begin{bmatrix}
1 & 2 & 2 & 1\\\
2 & 1 & 1 & 2\\\
2 & 1 & 2 & 1\\\
1 & 2 & 1 & 2\\\
\end{bmatrix}
\begin{bmatrix}
x_1 \\\
x_2 \\\
x_3 \\\
x_4 \end{bmatrix}=\begin{bmatrix}
1 \\\
1 \\\
1 \\\
1 \end{bmatrix}
$$

$a)$ To solve this system of linear equations using Gaussian Elimination, we perform the following row operations.

$$
\begin{align*}
R_2 &\rightarrow R_2 - 2R_1 \\
R_3 &\rightarrow R_3 - 2R_1 \\
R_4 &\rightarrow R_4 - R_1 \\
\end{align*}
$$

Thus, we get the following:

$$
\begin{bmatrix}
1 & 2 & 2 & 1\\\
0 & -3 & -3 & 0\\\
0 & -3 & -2 & -1\\\
0 & 0 & -1 & 1
\end{bmatrix}\begin{bmatrix}
x_1 \\\
x_2 \\\
x_3 \\\
x_4\end{bmatrix}=
\begin{bmatrix}
1 \\\
-1 \\\
-1 \\\
0 \end{bmatrix}
$$

In the next step, we perform $R_3 \rightarrow R_3 - R_2$ to get the following result:

$$
\begin{bmatrix}
1 & 2 & 2 & 1\\\
0 & -3 & -3 & 0\\\
0 & 0 & 1 & -1\\\
0 & 0 & -1 & 1 \end{bmatrix}
\begin{bmatrix}
x_1 \\\
x_2 \\\
x_3 \\\
x_4\end{bmatrix}=
\begin{bmatrix}
1 \\\
-1 \\\
0 \\\
0\end{bmatrix}
$$

Further, we perform $R_4 \rightarrow R_4 + R_3$ to get:

$$
\begin{bmatrix}
1 & 2 & 2 & 1\\\
0 & -3 & -3 & 0\\\
0 & 0 & 1 & -1\\\
0 & 0 & 0 & 0
\end{bmatrix} \begin{bmatrix}
x_1 \\\
x_2 \\\
x_3 \\\
x_4\end{bmatrix}=
\begin{bmatrix}
1 \\\
-1 \\\
0 \\\
0\end{bmatrix}
$$

As we can see, one of the equations is redundant since it becomes $0=0$. Hence, the system of equations has infinitely many solutions.
Here, the valid equations are:

$$
\begin{align*}
x_1 + 2x_2 + 2x_3 + x_4 &= 1 \\
3x_2 + 3x_3 &= 1 \\
x_3 &= x_4
\end{align*}
$$

Hence, to find the parametric solution, we use $x_3 = x_4 = \alpha$ and get:

$$
\begin{align*}
x_1 &= \frac{1-3\alpha}{3} \\\
x_2 &= \frac{1-3\alpha}{3} \\\
x_3 &= \alpha \\\
x_4 &= \alpha
\end{align*}
$$

where $\alpha \in \mathbb{R}$

$b)$ In the first step, we performed the following set of row operations

$$
\begin{align*}
R_2 &\rightarrow R_2 - 2R_1 \\
R_3 &\rightarrow R_3 - 2R_1 \\
R_4 &\rightarrow R_4 - R_1 \\
\end{align*}
$$

Hence, the corresponding matrix is:

$$
\mathbf T_1 =\begin{bmatrix}
1 & 0 & 0 & 0 \\\
-2 & 1 & 0 & 0 \\\
-2 & 0 & 1 & 0 \\\
-1 & 0 & 0 & 1 
\end{bmatrix}
$$

In the second step, we performed the operation:

$$
R_3 \rightarrow R_3 - R_2
$$ 

$$
\mathbf T_2 =
\begin{bmatrix}
1 & 0 & 0 & 0 \\\
0 & 1 & 0 & 0 \\\
0 & -1 & 1 & 0 \\\
0 & 0 & 0 & 1 \end{bmatrix}
$$

Similarly, for the final step, the operation performed is:

$$
R_4 \rightarrow R_4 + R_3
$$

$$
\mathbf T_3 =\begin{bmatrix}
1 & 0 & 0 & 0 \\\
0 & 1 & 0 & 0 \\\
0 & 0 & 1 & 0 \\\
0 & 0 & 1 & 1 \end{bmatrix}
$$

Thus, to find the corresponding matrix,

$$
\begin{align*}
\mathbf T &= \mathbf T_3 \mathbf T_2 \mathbf T_1 \\\
&= \begin{bmatrix}
1 & 0 & 0 & 0 \\\
0 & 1 & 0 & 0 \\\
0 & 0 & 1 & 0 \\\
0 & 0 & 1 & 1 
\end{bmatrix} 
\begin{bmatrix}
1 & 0 & 0 & 0 \\\
0 & 1 & 0 & 0 \\\
0 & -1 & 1 & 0 \\\
0 & 0 & 0 & 1
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0 & 0 \\\
-2 & 1 & 0 & 0 \\\
-2 & 0 & 1 & 0 \\\
-1 & 0 & 0 & 1 
\end{bmatrix} \\\
&= \begin{bmatrix}
1 & 0 & 0 & 0 \\\
-2 & 1 & 0 & 0 \\\
0 & -1 & 1 & 0 \\\
-1 & -1 & 1 & 1
\end{bmatrix}
\end{align*}
$$

$c)$
To find the Null Space of the matrix:

$$
\begin{bmatrix}
1 & 2 & 2 & 1 \\\
2 & 1 & 1 & 2 \\\
2 & 1 & 2 & 1 \\\
1 & 2 & 1 & 2 
\end{bmatrix} \begin{bmatrix}
x_1 \\\
x_2 \\\
x_3 \\\
x_4 \end{bmatrix}=
\begin{bmatrix}
0 \\\
0 \\\
0 \\\
0\end{bmatrix}
$$

Applying similar Gaussian Elimination as seen in part (a), we get:

$$
\begin{bmatrix}
1 & 2 & 2 & 1 \\\
0 & -3 & -3 & 0 \\\
0 & 0 & 1 & -1 \\\
0 & 0 & 0 & 0 
\end{bmatrix} \begin{bmatrix}
x_1 \\\
x_2 \\\
x_3 \\\
x_4 \end{bmatrix}=
\begin{bmatrix}
0 \\\
0 \\\
0 \\\
0\end{bmatrix}
$$

Here, we can see that one of the equations is redundant i.e. $0=0$. The other equations that we get are:

$$
\begin{align*}
x_1 + 2x_2 + 2x_3 + x_4 &= 0 \\
3x_2 + 3x_3 &= 0 \\
x_3 &= x_4
\end{align*}
$$

On using $x_3=x_4=\alpha$, we get the following solution in the parametric form:

$$
\begin{align*}
x_1= -\alpha\\
x_2= -\alpha\\
x_3=\alpha \\
x_4=\alpha \\
\end{align*}
$$

Hence, the null space contains all the vectors of the form 

$$
\mathbf{v} = \alpha \begin{bmatrix} -1 && -1 && 1 && 1 \end{bmatrix}^T
$$

where $\alpha$ is a constant.

$d)$

$$
\begin{bmatrix}
1 & 2 & 2 & 1 \\\
2 & 1 & 1 & 2 \\\
2 & 1 & 2 & 1 \\\
1 & 2 & 1 & 2 
\end{bmatrix}\begin{bmatrix}
x_1 \\\
x_2 \\\
x_3 \\\
x_4 \end{bmatrix}=
\begin{bmatrix}
1 \\
2 \\
3 \\
4 \\
\end{bmatrix}
$$

Using similar row operations as performed in earlier parts, we get:

$$
\begin{bmatrix}
1 & 2 & 2 & 1 \\\
0 & -3 & -3 & 0 \\\
0 & 0 & 1 & -1 \\\
0 & 0 & 0 & 0 
\end{bmatrix} \begin{bmatrix}
x_1 \\\
x_2 \\\
x_3 \\\
x_4 \end{bmatrix}=
\begin{bmatrix}
1 \\\
0 \\\
1 \\\
4\end{bmatrix}
$$

Here, one of the equations that we get is $0=4$, which is not possible. Hence, we can say that NO solutions exist for this case.

## Question 4
The column space of $\mathbf A \in \mathbb R^{m\times n}$ is defined as 

$$
\mathcal C(\mathbf A) := \set{\mathbf A \mathbf x | \mathbf x \in \mathbb R^n}
$$

and the left null space is defined as 

$$
\mathcal N(\mathbf A^T) := \set{\mathbf x \in \mathbb R^m | \mathbf A^T \mathbf x = \mathbf 0}
$$

Both, $\mathcal C(\mathbf A)$ and $\mathcal N(\mathbf A^T)$ are subspaces of $\mathbb R^m$. Along with that, we have proved in question $(2)$ that $\mathcal C(\mathbf A)$ and $\mathcal N(\mathbf A^T)$ are orthogonal to each other.

Let $\mathrm{rank}(\mathbf A) = r = \dim(\mathcal C(\mathbf{A}))$- then we can define an orthogonal basis $\set{\mathbf b_1,\cdots, \mathbf b_r}$ spanning the column space of $\mathbf A$.

As $\mathcal C(\mathbf A)$ is a subspace of $\mathbb R^{m}$, we extend the above orthogonal basis such that $\set{\mathbf b_1,\cdots, \mathbf b_r, \mathbf b_{r+1}, \cdots, \mathbf b_m}$ is an orthogonal basis of $\mathbb R^m$.

As any vector perpendicular to the column space of $\mathbf A$ belongs to the left null space of $\mathbf A^T$, and as the vectors $\mathbf b_{r+1}, \cdots, \mathbf b_m$ are perpendicular to the basis vectors of column space of $\mathbf A$, we can say that $\set{\mathbf b_{r+1}, \cdots, \mathbf b_m}$ is an orthogonal basis of $\mathcal N(\mathbf A^T)$.

Thus, we have 

$$
\begin{align*}
&\mathrm{dim}(\mathcal C(\mathbf A)) + \mathrm{dim}(\mathcal N(\mathbf A^T)) = m \\
\implies& \mathrm{rank}(\mathbf A) + \mathrm{dim}(\mathcal N(\mathbf A^T)) = m \\
\implies& \mathrm{dim(\mathcal N(\mathbf A^T))} = m - r\\
\end{align*}
$$ 

Using rank nullity theorem we have

$$
\begin{align*}
\mathrm{rank}(\mathbf A^T) &= m - \mathrm{dim}\left(\mathcal N(\mathbf A^T)\right)\\
&= m - (m-r) \\
&= r \\
&= \mathrm{rank}(\mathbf A) \\
\end{align*}
$$

<p align='right'>$\square$</p>

Let $\mathbf x \in \mathcal N(\mathbf A)$ where $\mathcal N(\mathbf A)$ is the null space for the matrix $\mathbf A$. Then, 

$$
\begin{align*}
&\mathbf A \mathbf x = \mathbf 0 \\
\implies& \mathbf A^T\mathbf A \mathbf x = \mathbf 0 \\
\implies& \mathbf x \in \mathcal N(\mathbf A^T\mathbf A) \\
\end{align*}
$$

As $\forall \mathbf x \in \mathcal N(\mathbf A)$  we have $\mathbf x \in \mathcal N(\mathbf A^T\mathbf A)$ implying $\mathcal N(\mathbf A) \subseteq \mathcal N(\mathbf A^T\mathbf A)$.

Let $\mathbf x \in \mathcal  N(\mathbf A^T\mathbf A)$ then

$$
\begin{align*}
&\mathbf A^T\mathbf A \mathbf x = \mathbf 0 \\
\implies& \mathbf x^T\mathbf A^T\mathbf A \mathbf x = \mathbf 0 \\
\implies& \left(\mathbf A \mathbf x\right)^T\left(\mathbf A \mathbf x\right) = \mathbf 0 \\
\implies& \mathbf A \mathbf x = \mathbf 0 \\
\implies& \mathbf x \in \mathcal N(\mathbf A) \\
\end{align*}
$$

As $\forall \mathbf x \in \mathcal N(\mathbf A^T\mathbf A)$  we have $\mathbf x \in \mathcal N(\mathbf A)$ implying $\mathcal N(\mathbf A^T\mathbf A) \subseteq \mathcal N(\mathbf A)$.

Thus, $\mathcal N(\mathbf A) = \mathcal N(\mathbf A^T\mathbf A)$.

Using rank nullity theorem we have 

$$
\begin{align*}
\mathrm{rank}(\mathbf A) &= n - \mathrm{dim}\left(\mathcal N(\mathbf A)\right)\\
\mathrm{rank}(\mathbf A^T\mathbf A) &= n - \mathrm{dim}\left(\mathcal N(\mathbf A^T\mathbf A)\right)\\
&= n - \mathrm{dim}\left(\mathcal N(\mathbf A)\right)
\end{align*}
$$

Thus, 

$$
\mathrm{rank}(\mathbf A) = \mathrm{rank}(\mathbf A^T\mathbf A) = \mathrm{rank}(\mathbf A^T) = \mathrm{rank}(\mathbf A\mathbf A^T)
$$

<p align='right'>$\square$</p>
