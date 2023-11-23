Matrix Theory: Assignment 5 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 5. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.

## Question 1
Let the two vectors be $\mathbf a, \mathbf b \in \mathbb{R}^2$. The transformation matrix to rotate the space by an angle $\theta$ in the anticlockwise direction is 

$$
\mathbf T(\theta) = \begin{bmatrix} \cos \theta & -\sin\theta \\\ \sin \theta & \cos \theta\end{bmatrix} \in \mathbb{R}^{2\times 2}
$$

Let the vectors obtained after rotation be $\mathbf{a'}, \mathbf{b'}$. Then we have: 

$$
\begin{align*}
\mathbf{a'} &= \mathbf T(\theta)\mathbf{a}\\
\mathbf{b'} &= \mathbf T(\theta)\mathbf{b}
\end{align*}
$$

$$
\begin{align*}
\implies d(\mathbf{a'}, \mathbf{b'}) &= \lVert \mathbf{a'} - \mathbf{b'} \rVert_2 \\
&= \lVert \mathbf T(\theta)\mathbf{a} - \mathbf T(\theta)\mathbf{b'} \rVert_2 \\
&= \left\lVert \begin{bmatrix} a_1\cos \theta -a_2 \sin \theta \\\ a_1\sin \theta + a_2\cos \theta\end{bmatrix} - \begin{bmatrix} b_1\cos \theta -b_2 \sin \theta \\\ b_1\sin \theta + b_2\cos \theta\end{bmatrix} \right\rVert_2 \\\
&= \left(\left(a_1\cos \theta - a_2\sin\theta -b_1\cos\theta + b_2\sin\theta\right)^2 + \left(a_1\sin \theta + a_2\cos \theta - b_1\sin\theta - b_2\cos\theta\right)^2\right)^{1\over 2}\\
&= \begin{pmatrix}(a_1-b_1)^2\cos^2 \theta + (a_2-b_2)^2\sin^2\theta - 2(a_1-b_1)(a_2-b_2)\cos\theta \sin\theta \\\ + (a_1-b_1)^2\sin^2\theta + (a_2-b_2)^2\cos^2\theta + 2(a_1-b_1)(a_2-b_2)\cos\theta\sin\theta\end{pmatrix}^{1\over 2} \\\
&= \left((a_1-b_1)^2 + (a_2 - b_2)^2\right)^{1\over 2} \\
&= \lVert \mathbf a - \mathbf b \rVert_2 = d(\mathbf a,\mathbf b)
\end{align*}
$$

<p align='right'>$\square$</p>

## Question 2

- The black box is a linear transformation from $\mathbb{R}^n \rightarrow \mathbb{R}^m$.
- Let $\mathbf{A}$ be the matrix associated with the black box. The matrix is of the dimensions $m \times n$.
- Let $\mathbf{x} \in \mathbb{R}^n$ be the input to the black box.
- Let $\mathbf{y} \in \mathbb{R}^m$ be the output from the black box.


$$
\begin{align*}
\mathbf A\mathbf x=\mathbf y
\end{align*}
$$

To find the first column, we give an input vector with all zeros except the first element, which we set as $1$. Then, the output vector will be the first column of the matrix $\mathbf A$. 

$$
\begin{align*}
\mathbf x &= \begin{bmatrix}
    1 & 0 & 0 & \dots & 0
\end{bmatrix}^T \\
\implies \mathbf A\mathbf x &= \begin{bmatrix}
    a_{11} & a_{21} & a_{31} & \dots & a_{m1}
    \end{bmatrix}^T = \mathbf y
\end{align*}
$$

We repeat this process with all the other columns to find the matrix $\mathbf A$.
To find the second column of the matrix $\mathbf A$, we use the input vector as:

$$
\mathbf x = \begin{bmatrix}0 & 1 & 0 & \dots & 0\end{bmatrix}^T
$$

Using $\mathbf A\mathbf x=\mathbf y$ we get the second column of the matrix $\mathbf A$. 

We repeat this process until we get all the columns of the matrix $\mathbf A$.

## Question 3
$a)$ Let $\mathbf x \in \mathbb{R}^n$,  We can represent $\mathbf x$ as 

$$
\begin{align*}
\mathbf x &= \mathbf y\big|_\text{basis $\mathbb B$} \\
&= y_1\mathbf b_1 + y_2\mathbf b_2 + \dots + y_n\mathbf b_n\\
&= \begin{bmatrix}\mathbf b_1 & \mathbf b_2 & \cdots & \mathbf b_n\end{bmatrix}\mathbf y \\
&= \mathbf B\mathbf y
\end{align*}
$$ 

where $\mathbf B$ is the matrix with columns as the basis vectors $\mathbf b_1, \mathbf b_2, \dots, \mathbf b_n$ and $\mathbf y$ is the coordinate vector of $\mathbf x$ in basis $\mathbb B$.

Similarly, we can write that 

$$
\begin{align*}
\mathbf{x} &= \mathbf z\big|_\text{basis $\mathbb V$} \\
&= \begin{bmatrix} \mathbf v_1 & \mathbf v_2 & \cdots & \mathbf v_n\end{bmatrix}\mathbf z \\
&= \mathbf V\mathbf z
\end{align*}
$$

where $\mathbf V$ is the matrix with columns as the basis vectors $\mathbf v_1, \mathbf v_2, \dots, \mathbf v_n$ and $\mathbf z$ is the coordinate vector of $\mathbf x$ in basis $\mathbb V$.

Now, we have defined a transformation $\mathbf T: \mathbb R^n \rightarrow \mathbb R^n$ such that $\mathbf T(\mathbf y) = \mathbf z$.

To prove that $\mathbf T$ is a linear transformation, we consider vectors $\mathbf y_1$ and $\mathbf y_2$, which are the coordinate vectors of $\mathbf x_1$ and $\mathbf x_2$ in the basis $\mathbb B$ respectively. Similarly, consider $\mathbf z_1$ and $\mathbf z_2$  which are the coordinate vectors of $\mathbf x_1$ and $\mathbf x_2$ in the basis $\mathbb V$ respectively.

$$
\begin{align*}
\implies \mathbf B \mathbf y_1 &= \mathbf x_1 = \mathbf V \mathbf z_1 \\
\implies \mathbf B \mathbf y_2 &= \mathbf x_2 = \mathbf V \mathbf z_2 \\
\implies \mathbf B\left(\alpha  \mathbf y_1 + \beta \mathbf y_2\right) &= \mathbf V\left(\alpha \mathbf z_1 + \beta \mathbf z_2\right)  \quad \forall \alpha,\beta \in \mathbb R
\end{align*}
$$

Since $\mathbf T(\mathbf y) = \mathbf z$, we have:

$$
\begin{align*}
\implies \mathbf T(\alpha\mathbf y_1 + \beta\mathbf y_2) &= \alpha \mathbf z_1 + \beta \mathbf z_2 \\
&= \alpha \mathbf T(\mathbf y_1) + \beta \mathbf T(\mathbf y_2) \quad \forall \alpha,\beta \in \mathbb R
\end{align*}
$$

Thus, $\mathbf T$ is a linear transformation.

<p align='right'>$\square$</p>

$b)$ As $\mathbf T$ is a linear transformation, we can associate a matrix $\mathbf A$ with it such that $\mathbf T(\mathbf y) = \mathbf A\mathbf y$ = $\mathbf z$.

$\mathbf v_1, \mathbf v_2, \dots, \mathbf v_n$ are basis vectors which form the columns of the matrix $\mathbf B$. Basis vectors are by definition, independent. Hence, the columns of the matrix obtained above are also independent. Therefore, $\mathbf B$ is invertible.

$$
\begin{align*}
\mathbf V \mathbf z &= \mathbf B \mathbf y \\
\implies \mathbf z &= \mathbf V^{-1}\mathbf B \mathbf y \\ 
\implies \mathbf T(\mathbf y) &= \mathbf V^{-1}\mathbf B \mathbf y \\
\implies \mathbf A &= \mathbf V^{-1}\mathbf B
\end{align*}
$$

Thus, the matrix $\mathbf A$ is the change of basis matrix from $\mathbb B$ to $\mathbb V$.

## Question 4

Let $\mathbf{x} \in \mathbf{V}$. 

$$
\mathbf{x}=c_{1}\mathbf{v_{1}}+c_{2}\mathbf{v_{2}}+\cdots c_{n}\mathbf{v_{n}}
$$

Thus, the coordinate vector of $\mathbf{x}$ is 

$$
\mathbf{y} = \begin{bmatrix} c_{1}\\\ c_{2}\\\ \vdots \\\ c_{n} \end{bmatrix}
$$

$$
\mathbf T(\mathbf{x})=\mathbf T(c_{1}\mathbf{v_{1}}+c_{2}\mathbf{v_{2}}+\cdots c_{n}\mathbf{v_{n}}) 
$$

As matrices are linear transformations by definition: 

$$
\mathbf T(\mathbf{x})=\mathbf T(c_{1}\mathbf{v_{1}})+\mathbf T(c_{2}\mathbf{v_{2}}) + \cdots + \mathbf T(c_{n}\mathbf{v_{n}})
$$ 

$$
=c_{1}\mathbf T(\mathbf{v_{1}})+c_{2}T(\mathbf{v_{2}})+ \cdots + c_{n}T(\mathbf{v_{n}})
$$

Now, $\mathbf T(\mathbf{v_{1}})$ can be represented in basis $W$ as 

$$
\mathbf T(\mathbf{v_{1}})=a_{11}\mathbf{w_{1}}+a_{21}\mathbf{w_{2}}+\cdots a_{m1}\mathbf{w_{m}}
$$

Similarly, 

$$
\mathbf T(\mathbf{v_{2}})=a_{12}\mathbf{w_{1}}+a_{22}\mathbf{w_{2}}+\cdots a_{m2}\mathbf{w_{m}}
$$ 

And so on, until:

$$
\mathbf T(\mathbf{v_{n}})=a_{1n}\mathbf{w_{1}}+a_{2n}\mathbf{w_{2}}+\cdots a_{mn}\mathbf{w_{m}}
$$ 

Therefore, 

$$
\mathbf  T(\mathbf{x})=c_{1}(a_{11}\mathbf{w_{1}}+a_{21}\mathbf{w_{2}}+\cdots + a_{m1}\mathbf{w_{m}})+c_{2}(a_{12}\mathbf{w_{1}}+a_{22}\mathbf{w_{2}}+\cdots + a_{m2}\mathbf{w_{m}}) + \cdots +c_{n}(a_{1n}\mathbf{w_{1}}+a_{2n}\mathbf{w_{2}}+\cdots + a_{mn}\mathbf{w_{m}})
$$

$$
=\mathbf{w_{1}}(c_{1}a_{11}+\cdots +c_{n}a_{1n})+\mathbf{w_{2}}(c_{1}a_{21}+\cdots +c_{n}a_{2n})+\cdots + \mathbf{w_{m}}(c_{1}a_{m1}+\cdots +c_{n}a_{mn})
$$ 

$$
\implies \mathbf T(\mathbf{y}) _ \text{basis $W$} = 
  \begin{bmatrix}
    a_{11} & a_{12} & \cdots & a_{1n} \\
    a_{21} & a_{22} & \cdots & a_{2n} \\
     \vdots & \vdots & \cdots & \vdots \\
    a_{m1} & a_{m2} & \cdots & a_{mn}
  \end{bmatrix}
  \begin{bmatrix} c_{1}\\\ c_{2}\\\ \vdots\\\ c_{n}
  \end{bmatrix}
  = \mathbf A\mathbf{y}
$$

<p align='right'>$\square$</p>

## Question 5

Given a matrix

$$
\mathbf{A} = \begin{bmatrix}1&-1&0&0 \\\
0&1&-1&0 \\\
0&0&1&-1 \\\
0&0&0&1 
\end{bmatrix}
$$

let $\mathbf{A}$ be a linear transformation $\mathbf{A}: \mathbb{R}^4 \rightarrow \mathbb{R}^4$.

$\mathbf{A}$ is a linear transformation that takes a vector $\mathbf{x} \in \mathbb{R}^4$ and returns a vector $\mathbf{y} \in \mathbb{R}^4$ such that $\mathbf{y} = \mathbf{Ax}$.

$\mathbf{A}^{-1}$ is a linear transformation that takes a vector $\mathbf{y} \in \mathbb{R}^4$ and returns a vector $\mathbf{x} \in \mathbb{R}^4$ such that $\mathbf{x} = \mathbf{A}^{-1}\mathbf{y}$.

Let 

$$
\mathbf x = \begin{bmatrix}x_1 \\\ x_2 \\\ x_3 \\\ x_4\end{bmatrix} \in \mathbb{R}^4
$$

$$ 
\begin{align*}
\mathbf{A} \mathbf{x} &= \begin{bmatrix} 1 & -1 & 0 & 0 \\
0 & 1 & -1 & 0 \\
0 & 0 & 1 & -1 \\
0 & 0 & 0 & 1 \end{bmatrix}
\begin{bmatrix} x_1 \\
 x_2 \\
  x_3 \\
   x_4 \end{bmatrix} \\
\begin{bmatrix} y_1 \\\ y_2 \\\ y_3 \\\ y_4 \end{bmatrix} &= \begin{bmatrix} x_1 - x_2 \\\ x_2 - x_3 \\\ x_3 - x_4 \\\ x_4 \end{bmatrix}
\end{align*} 
$$

The above equation can be written as:

$$
\begin{align*}
y_1 &= x_1 - x_2 \\
y_2 &= x_2 - x_3 \\
y_3 &= x_3 - x_4 \\
y_4 &= x_4
\end{align*}
$$

From the above equations, we can write:

$$
\begin{align*}
x_4 &= y_4 \\
x_3 &= y_3 + x_4 = y_3 + y_4 \\
x_2 &= y_2 + x_3 = y_2 + y_3 + y_4 \\
x_1 &= y_1 + x_2 = y_1 + y_2 + y_3 + y_4
\end{align*}
$$

Therefore, 

$$ 
\mathbf{x} = \begin{bmatrix} 0&0&0&1 \\\
0&0&1&1\\\
0&1&1&1\\\
1&1&1&1 
\end{bmatrix}
\mathbf{y}
$$

Therefore, $\mathbf{A}^{-1}$ is a linear transformation that takes a vector $\mathbf{y} \in \mathbb{R}^4$ and returns a vector $\mathbf{x} \in \mathbb{R}^4$ such that $\mathbf{x} = \mathbf{A}^{-1}\mathbf{y}$.

$$ \implies \mathbf{A}^{-1} = \begin{bmatrix} 0&0&0&1 \\
0&0&1&1\\
0&1&1&1\\
1&1&1&1 \end{bmatrix} $$

## Question 6
Given $\mathbf{T}$ denotes a transformation that corresponds to rotating a vector by angle $\theta$ in the counter-clockwise direction (about the x−axis) and $\mathbf{T_1}$ denotes a transformation that corresponds to reflection about a given vector $\mathbf{v} \in \mathbb{R}^2$. 

As $\mathbf{T}$ and $\mathbf{T_1}$ are tranformations corresponding to rotation and reflection respectively, they are linear transformations, i.e., we have 

$$
\begin{align*}
\mathbf{T}\left(\mathbf{x_1} + \mathbf{x_2}\right) &= \mathbf{T}\left(\mathbf{x_1}\right) + \mathbf{T}\left(\mathbf{x_2}\right)\\
\mathbf{T}\left(\mathbf{\alpha x_3}\right) &= \alpha \mathbf{T}\left(\mathbf{x_3}\right)\\
\mathbf{T_1}\left(\mathbf{x_1} + \mathbf{x_2}\right) &= \mathbf{T_1}\left(\mathbf{x_1}\right) + \mathbf{T_1}\left(\mathbf{x_2}\right)\\
\mathbf{T_1}\left(\mathbf{\alpha x_3}\right) &= \alpha \mathbf{T_1}\left(\mathbf{x_3}\right)\\
\end{align*}
$$

where $\mathbf{x_1}$, $\mathbf{x_1}$, and $\mathbf{x_3}$ are vectors $\in \mathbb{R}^2$ and $\alpha$ is a scalar $\in \mathbb{C}$.

We have $\mathbf{T_2}\left(\mathbf{x}\right):= \mathbf{T}\left(\mathbf{T_1}\left(\mathbf{x}\right)\right)$

$a)$  To show that $\mathbf{T_2}\left(\mathbf{x}\right)$ is a linear transformation, we must show homogenity and additivity.
Consider transformations over two vectors $\mathbf{x_1}$ and $\mathbf{x_2}$ $\in \mathbb{R}^2$.

$$
\begin{align*}
\mathbf{T_2}\left(\mathbf{x_1} + \mathbf{x_2}\right) &= \mathbf{T}\left(\mathbf{T_1}\left(\mathbf{x_1} + \mathbf{x_2}\right)\right)\\
\implies \mathbf{T_2}\left(\mathbf{x_1} + \mathbf{x_2}\right) &= \mathbf{T}\left(\mathbf{T_1}\left(\mathbf{x_1}\right) + \mathbf{T_1}\left(\mathbf{x_2}\right)\right)\\
\implies \mathbf{T_2}\left(\mathbf{x_1} + \mathbf{x_2}\right) &= \mathbf{T}\left(\left(\mathbf{T_1}\left(\mathbf{x_1}\right)\right)\right) + \mathbf{T}\left(\left(\mathbf{T_1}\left(\mathbf{x_2}\right)\right)\right)\\
\implies \mathbf{T_2}\left(\mathbf{x_1} + \mathbf{x_2}\right) &= \mathbf{T_2}\left(\mathbf{x_1}\right) + \mathbf{T_2}\left(\mathbf{x_2}\right)\\
\end{align*}
$$

This shows that additivity is satisfied.

Now, consider a scalar $\alpha \in \mathbb{C}$ and the vector $\mathbf{x_3}\in \mathbb{R}^2$.

$$
\begin{align*}
\mathbf{T_2}\left(\mathbf{\alpha x_3}\right) &= \mathbf{T}\left(\mathbf{T_1}\left(\mathbf{\alpha x_3}\right)\right)\\
\implies \mathbf{T_2}\left(\mathbf{\alpha x_3}\right) &= \mathbf{T}\left(\alpha \mathbf{T_1}\left(\mathbf{x_3}\right)\right)\\
\implies \mathbf{T_2}\left(\mathbf{\alpha x_3}\right) &= \alpha \mathbf{T}\left(\mathbf{T_1}\left(\mathbf{x_3}\right)\right)\\
\implies \mathbf{T_2}\left(\mathbf{\alpha x_3}\right) &= \alpha \mathbf{T_2}\left(\mathbf{x_3}\right)\\
\end{align*}
$$

This shows that homogenity is satisfied.

From the two proofs above, we can conclude that $\mathbf{T_2}\left(\mathbf{x}\right)$ is a linear transformation.

$b)$ To find the matrix representation of $\mathbf{T_2}$, we first find the matrix representation of $\mathbf{T}$ and $\mathbf{T_1}$.

Any linear tranformation can be repeesented in the form of a matrix-vector product i.e., $\mathbf{T}\left(\mathbf{x}\right) = \mathbf{A}\mathbf{x}$ where $\mathbf{A}$ is the matrix representation of $\mathbf{T}$ and $\mathbf{x}$ is the vector representation of $\mathbf{x}$.

The transformation matrix $\mathbf{T}$ that causes a rotation by angle $\theta$ in counter-clockwise direction (about the x−axis), is: 

$$
\mathbf{T}\left(\mathbf{x}\right) := \begin{bmatrix} \cos\theta & -\sin\theta \\\ \sin\theta & \cos\theta \end{bmatrix} \mathbf{x}
$$

The transformation matrix $\mathbf{T_1}$ that causes reflection about a given vector $\mathbf{v} \in \mathbb{R}^2$ by some angle, say $\phi$ , is: 

$$
\mathbf{T_1}\left(\mathbf{x}\right) := \begin{bmatrix} \cos 2\phi & \sin 2\phi \\\ \sin 2\phi & -\cos 2\phi \end{bmatrix} \mathbf{x}
$$

Now, we find the matrix representation of $\mathbf{T_2}$ as follows:

$$
\begin{align*}
\mathbf{T_2}\left(\mathbf{x}\right)&:= \mathbf{T}\left(\mathbf{T_1}\left(\mathbf{x}\right)\right)\\
&= \begin{bmatrix} \cos\theta & -\sin\theta \\\ \sin\theta & \cos\theta\end{bmatrix}\begin{bmatrix} \cos 2\phi & \sin 2\phi \\\ \sin 2\phi & -\cos 2\phi \end{bmatrix} \mathbf{x}\\
&= \begin{bmatrix} \cos \theta \cos 2\phi \ - \sin\theta \sin 2\phi  & \cos\theta \sin 2\phi \ + \sin\theta \cos 2\phi \\\ \sin\theta \cos 2\phi \ + \cos\theta \sin 2\phi & \sin\theta \sin 2\phi \ - \cos\theta \cos 2\phi \end{bmatrix} \mathbf{x}\\
&= \begin{bmatrix} \cos\left(\theta + 2\phi\right)  & \sin \left(2\phi + \theta\right) \\\ \sin \left(\theta + 2\phi \right) & -\cos\left(2\phi +\theta \right) \end{bmatrix} \mathbf{x}
\end{align*}
$$



