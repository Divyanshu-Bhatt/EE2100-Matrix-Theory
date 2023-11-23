Matrix Theory: Assignment 10 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 10. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.

## Question 1

$\underline{\textbf{NOTE:}}$ The property mentioned in the question holds only for real skew-symmetric matrices and we will show the proof for the same. If we wanted to prove this property for complex matrices, then $\mathbf{A}$ would have to be a skew-hermitian matrix. The structure of the proof would remain the same in both cases. 

Given $\mathbf{A}$ is a skew-symmetric matrix $\implies \mathbf{A}^{T} = - \mathbf{A}$. Now,

$$
\mathbf{Ax = \lambda x}
$$

The norm of the vector $\mathbf{Ax}$ is given as 

$$
\begin{align*}
{\lVert \mathbf{Ax} \rVert}^2_2 &= ((\mathbf{Ax})^\*)^T\mathbf{Ax} \\
&= (\mathbf{x}^\*)^T\mathbf{A}^T\mathbf{Ax} \\
&= -(\mathbf{x}^\*)^T\mathbf{A}^2\mathbf{x} \\
&= -(\mathbf{x}^\*)^T\mathbf{\lambda}^2\mathbf{x} \\
&= -\lambda^2 \lVert \mathbf{x} \rVert^2_2 \\
\implies \lambda^2 &= -{\lVert \mathbf{Ax} \rVert^2_2 \over \lVert \mathbf{x} \rVert^2_2}
\end{align*}
$$

The final equation indicates that $\lambda^2$ must take a negative value (since $\lVert \mathbf{Ax} \rVert^2_2 \over \lVert \mathbf{x} \rVert^2_2$ is always positive) which is only possible if $\lambda$ is purely imaginary. Thus the eigenvalues of $\,\mathbf{A}$ are purely imaginary.

## Question 2

Given $\mathbf{A} \in \mathbb{R^{m\times n}}$, whose column vectors are linearly independent, we want to prove that the eigen values of $\mathbf{A^T A}$ are purely real and positive.

For this, let $\lambda$ denote the eigen values and $\mathbf{x}$ denote the respective eigen vector of matrix $\mathbf{A^T A}$. Hence,

$$
\begin{align*}
\mathbf{A^T Ax}&=\mathbf{\lambda x} \\
\mathbf{x^T}\mathbf{A^T Ax}&=\mathbf{\lambda x^T x} \\
(\mathbf{x^T A^T})(\mathbf{Ax}) &= \mathbf{\lambda x^T x} \\
\mathbf{(Ax)^T}\mathbf{(Ax)} &= \mathbf{\lambda x^T x} \\
\mathbf{\lVert Ax \rVert}_2^2 &= \lambda \mathbf{\lVert x\rVert}_2^2\\
\lambda &= \frac{\mathbf{\lVert Ax \rVert}_2^2}{\mathbf{\lVert x\rVert}_2^2}
\end{align*}
$$

Since the norms are purely real and positive, we can see that $\mathbf{\lambda}$ is also purely real and positive.

## Question 3 

$a)$

$$
\mathbf{A_1} = \begin{bmatrix} 0&1&0 \\\ 0&0&1 \\\ 1&0&0 \end{bmatrix}
$$

The characteristic polynomial of $\mathbf{A}$ is given by 

$$
\begin{align*}
p(\lambda) &= \det(\mathbf{A_1} - \lambda \mathbf{I}) \\
&= \det \begin{bmatrix} -\lambda&1&0 \\\ 0&-\lambda&1 \\\ 1&0&-\lambda \end{bmatrix} \\
&= -\lambda \det \begin{bmatrix} -\lambda&1 \\\ 0&-\lambda \end{bmatrix} - \det \begin{bmatrix} 0&1 \\\ 1&-\lambda \end{bmatrix} \\
&= -\lambda^3 + 1 \\
&= -(\lambda - 1)(\lambda^2 + \lambda + 1)
\end{align*}
$$

The eigen values of $\mathbf{A_1}$ are given by the roots of the characteristic polynomial, i.e., $\lambda_1 = 1$, $\lambda_2 = \frac{-1 + i\sqrt{3}}{2}$ and $\lambda_3 = \frac{-1 - i\sqrt{3}}{2}$

The eigen vectors corresponding to $\lambda_1 = 1$ is given by

$$
\begin{align*}
(\mathbf{A_1} - \lambda_1 \mathbf{I})\mathbf{x} &= \mathbf{0} \\
\begin{bmatrix} -1&1&0 \\\ 0&-1&1 \\\ 1&0&-1 \end{bmatrix} \mathbf{x} &= \mathbf{0} \\
\end{align*}
$$

Solving above equation, we get $\mathbf{x} = t\left[1 \quad 1 \quad 1\right]^T$

The eigen vectors corresponding to $\lambda_2 = \frac{-1 + i\sqrt{3}}{2}$ is given by

$$
\begin{align*}
(\mathbf{A_1} - \lambda_2 \mathbf{I})\mathbf{x} &= \mathbf{0} \\
\begin{bmatrix} \frac{1 - i\sqrt{3}}{2}&1&0 \\\ 0&\frac{1 - i\sqrt{3}}{2}&1 \\\ 1&0&\frac{1 - i\sqrt{3}}{2} \end{bmatrix} \mathbf{x} &= \mathbf{0} \\
\end{align*}
$$

Solution of above equation is given by $\mathbf{x} = t\left[1 \quad \frac{-1 + i\sqrt{3}}{2} \quad \frac{-1 - i\sqrt{3}}{2} \right]^T$

The eigen vectors corresponding to $\lambda_3 = \frac{-1 - i\sqrt{3}}{2}$ is given by

$$
\begin{align*}
(\mathbf{A_1} - \lambda_3 \mathbf{I})\mathbf{x} &= \mathbf{0} \\
\begin{bmatrix} \frac{1 + i\sqrt{3}}{2}&1&0 \\\ 0&\frac{1 + i\sqrt{3}}{2}&1 \\\ 1&0&\frac{1 + i\sqrt{3}}{2} \end{bmatrix} \mathbf{x} &= \mathbf{0} \\
\end{align*}
$$

Solution of above equation is given by $\mathbf{x} = t\left[1\quad \frac{-1 - i\sqrt{3}}{2}\quad \frac{-1 + i\sqrt{3}}{2}\right]^T$

To summarize, the eigen values and eigen vectors of $\mathbf{A_1}$ are given by

$$
\begin{align*}
\lambda_1 &= 1, \mathbf{x_1} = {1\over \sqrt{3}}\begin{bmatrix} 1 \\\ 1 \\\ 1 \end{bmatrix} \\
\lambda_2 &= \frac{-1 + i\sqrt{3}}{2}, \mathbf{x_2} = {1\over \sqrt{3}}\begin{bmatrix} 1 \\\ \frac{-1 + i\sqrt{3}}{2} \\\ \frac{-1 - i\sqrt{3}}{2} \end{bmatrix} \\
\lambda_3 &= \frac{-1 - i\sqrt{3}}{2}, \mathbf{x_3} = {1\over \sqrt{3}}\begin{bmatrix} 1 \\\ \frac{-1 - i\sqrt{3}}{2} \\\ \frac{-1 + i\sqrt{3}}{2} \end{bmatrix}
\end{align*}
$$

$b)$

$$
\mathbf{A_2} = \begin{bmatrix} 1&1&1 \\\ 1&1&1 \\\ 1&1&1 \end{bmatrix}
$$

The characteristic polynomial of $\mathbf{A}$ is given by

$$
\begin{align*}
p(\lambda) &= \det(\mathbf{A_2} - \lambda \mathbf{I}) \\
&= \det \begin{bmatrix} 1 - \lambda&1&1 \\\ 1&1 - \lambda&1 \\\ 1&1&1 - \lambda \end{bmatrix} \\
&= (1 - \lambda) \det \begin{bmatrix} 1 - \lambda&1 \\\ 1&1 - \lambda \end{bmatrix} - \det \begin{bmatrix} 1&1 \\\ 1&1 - \lambda \end{bmatrix} + \det \begin{bmatrix} 1&1 - \lambda \\\ 1&1 \end{bmatrix} \\
&= (1 - \lambda) (\lambda^2 - 2\lambda) + \lambda + \lambda\\
&= \lambda^2 - 2\lambda + \lambda^3 - 2\lambda^2 + \lambda + \lambda \\
&= \lambda^3 - \lambda^2 \\
&= \lambda^2(\lambda - 1)
\end{align*}
$$

The eigen values of $\mathbf{A_2}$ are given by the roots of the characteristic polynomial, i.e., $\lambda_1 = 1$, $\lambda_2 = \lambda_3 = 0$

The eigen vectors corresponding to $\lambda_1 = 1$ is given by

$$
\begin{align*}
(\mathbf{A_2} - \lambda_1 \mathbf{I})\mathbf{x} &= \mathbf{0} \\
\begin{bmatrix} 0&1&1 \\\ 1&0&1 \\\ 1&1&0 \end{bmatrix} \mathbf{x} &= \mathbf{0} \\
\end{align*}
$$

Solving above equation, we get $\mathbf{x}$ = \left[\right]^T$.

The eigen vectors corresponding to $\lambda_2 = \lambda_3 = 0$ is given by

$$
\begin{align*}
(\mathbf{A_2} - \lambda_2 \mathbf{I})\mathbf{x} &= \mathbf{0} \\
\begin{bmatrix} 1&1&1 \\\ 1&1&1 \\\ 1&1&1 \end{bmatrix} \mathbf{x} &= \mathbf{0} \\
\end{align*}
$$

Solution of above equation is given by $\mathbf{x} = t\left[1 \quad -1 \quad 0 \right]^T + s\left[1 \quad 0 \quad -1\right]^T$

to summarize, the eigen values and eigen vectors of $\mathbf{A_2}$ are given by

$$
\begin{align*}
\lambda_1 &= 1, \mathbf{x_1} = \begin{bmatrix} 1 \\\ 1 \\\ 1 \end{bmatrix} \\
\lambda_2 &= \lambda_3 = 0, \mathbf{x_2} = \begin{bmatrix} 1 \\\ -1 \\\ 0 \end{bmatrix}, \mathbf{x_3} = \begin{bmatrix} 1 \\\ 0 \\\ -1 \end{bmatrix}
\end{align*}
$$

## Question 4
The given proposition is false. We will prove this by giving a counter example. Consider the $3 \times 3$ matrix $\mathbf{A}$, such that

$$
\mathbf{A}=\begin{bmatrix}
0 & 1 &1 \\\
1 & 0 & 1 \\\
1 & 1 & 0
\end{bmatrix}
$$

We first solve the characteristic equation:

$$
\mathrm{det}(\mathbf{A-\lambda I})=0
$$

$$
\mathbf{A-\lambda I}=\begin{bmatrix}
-\lambda & 1 &1 \\
1 & -\lambda & 1 \\
1 & 1 & -\lambda
\end{bmatrix}
$$

$$
\begin{align*}
\implies& -\lambda(\lambda^2-1)-1(-\lambda-1)+1(1-(-\lambda))=0 \\
\implies& \lambda^3-3\lambda+2=0 \\
\implies& (\lambda+1)^2(\lambda-2)=0 \\
\end{align*}
$$

So, the eigen values are $\lambda_1=\lambda_2=-1$ and $\lambda_3=2$.

Finding the eigenvectors corresponding to the eigenvalue $\lambda = -1$

$$
\begin{align*}
&\begin{bmatrix}
0 & 1 &1 \\
1 & 0 & 1 \\
1 & 1 & 0
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
x_3
\end{bmatrix}=
(-1)\begin{bmatrix}
x_1 \\
x_2 \\
x_3
\end{bmatrix}\\
\implies & \begin{bmatrix}
1 & 1 &1 \\
1 & 1 & 1 \\
1 & 1 & 1
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
x_3
\end{bmatrix}=
\begin{bmatrix}
0 \\
0 \\
0
\end{bmatrix}
\end{align*}
$$

Thus, 

$$
x_1+x_2+x_3=0
$$

$$
\begin{align*}
\implies  \mathbf{x}&=\begin{bmatrix}
\alpha \\
\beta \\
-\alpha - \beta 
\end{bmatrix}\\
&=\alpha\begin{bmatrix}
1 \\
0 \\
-1
\end{bmatrix} + \beta \begin{bmatrix}
0 \\
1 \\
-1
\end{bmatrix}
\end{align*}
$$

Thus, the eigenvectors corresponding to the eigenvalue $\lambda = -1$ are:

$$
\mathbf{x}={1\over \sqrt{2}}\begin{bmatrix}
1 \\
0 \\
-1
\end{bmatrix}
\quad 
\mathbf{x}={1\over \sqrt{2}}\begin{bmatrix}
0 \\
1 \\
-1
\end{bmatrix}
$$

Finding the eigenvectors corresponding to the eigenvalue $\lambda = 2$

$$
\begin{align*}
&\begin{bmatrix}
0 & 1 &1 \\
1 & 0 & 1 \\
1 & 1 & 0
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
x_3
\end{bmatrix}=
2\begin{bmatrix}
x_1 \\
x_2 \\
x_3
\end{bmatrix}\\
\implies & \begin{bmatrix}
-2 & 1 &1 \\
1 & -2 & 1 \\
1 & 1 & -2
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
x_3
\end{bmatrix}=
\begin{bmatrix}
0 \\
0 \\
0
\end{bmatrix}\\
\implies & \begin{bmatrix}
-2 & 1 &1 \\
0 & -1.5 & 1.5 \\
0 & 0 & 0
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2 \\
x_3
\end{bmatrix}=
\begin{bmatrix}
0 \\
0 \\
0
\end{bmatrix}\\
\end{align*}
$$

Thus, 

$$
\begin{align*}
&-2x_1+x_2+x_3=0 \\
&-1.5x_2+1.5x_3=0 \\
\implies& \mathbf{x} = \begin{bmatrix}
\alpha \\
\alpha \\
\alpha
\end{bmatrix}
\end{align*}
$$

Thus, the eigenvectors corresponding to the eigenvalue $\lambda = 2$ is:

$$
\mathbf{x}={1\over \sqrt{3}}\begin{bmatrix}
1 \\
1 \\
1
\end{bmatrix}
$$

As we can see from the above example that the eigenvectors are independent of each other but the eigenvalues are not distinct. Thus, the given proposition is false.

The converse of the above proposition is true i.e if the eigenvalues are distinct then the eigenvectors are independent of each other.

## Question 5
Given matrix as follows:

$$
\mathbf{A}=\begin{bmatrix}
			6  & -2 & -1 \\
			3  & 1  & -1 \\  
			2  & -1  & 2 \\
			\end{bmatrix}
$$

As it is a 3 by 3 matrix, we use $\mathbf{I}_3$ as the identity matrix. This gives us the characteristic equaiton:

$$
\det(\mathbf{A}-\lambda\mathbf{I}_3) = 0 \\
$$

$$
\implies \det \begin{bmatrix}
			6-\lambda  & -2 & -1 \\
			3  & 1-\lambda  & -1 \\  
			2  & -1  & 2-\lambda \\
			\end{bmatrix} = 0 \\
$$

$$
\begin{align*}
&\implies (6-\lambda)\left[(1-\lambda)(2-\lambda)-1\right] + 2\left[3(2-\lambda)+2\right] - \left[3(-1)-2(1-\lambda)\right] = 0 \\
&\implies (6-\lambda)\left[\lambda^2-3\lambda+1\right] + 2\left[6-3\lambda+2\right] - \left[-3-2+2\lambda\right] = 0 \\
&\implies (6-\lambda)\left[\lambda^2-3\lambda+1\right] + 2\left[8-3\lambda\right] - \left[-5+2\lambda\right] = 0 \\
&\implies (6-\lambda)\left[\lambda^2-3\lambda+1\right] + 16-6\lambda + 5-2\lambda = 0 \\
&\implies 6\lambda^2 - 18\lambda + 6 - \lambda^3 + 3\lambda^2 - \lambda - 8\lambda + 21 = 0 \\
&\implies -\lambda^3 + 9\lambda^2 - 27\lambda + 27 = 0 \\
&\implies \lambda^3 - 9\lambda^2 + 27\lambda - 27 = 0 \\
&\implies (\lambda-3)^3 = 0 \\
&\implies \lambda = 3,3,3
\end{align*}
$$

Note that the algebraic multiplicity of the eigen value 3 is 3. We now find the corresponding eigen vectors. We have:

$$
\left(\mathbf{A}-\lambda\mathbf{I}_3\right)\mathbf{v} = \mathbf{0} \\
$$

$$
\implies \begin{bmatrix} 3  & -2 & -1 \\\ 3  & -2  & -1 \\\ 2  & -1  & -1\end{bmatrix}
\begin{bmatrix} v_1\\\v_2\\\v_3\end{bmatrix} = \begin{bmatrix} 0\\\0\\\0\end{bmatrix}
$$

On swapping the last 2 rows and performing Row Substitutitons, we get:

$$
\begin{align*}
\begin{bmatrix} 3  & -2 & -1 \\\ 0  & 1  & -1 \\\ 0  & 0  & 0\end{bmatrix}\begin{bmatrix} v_1\\\v_2\\\v_3\end{bmatrix} &= \begin{bmatrix} 0\\\0\\\0\end{bmatrix} \\
\implies \mathbf{v} = \begin{bmatrix}\alpha \\\ \alpha \\\ \alpha\end{bmatrix} &= \alpha
\begin{bmatrix}1 \\\ 1 \\\ 1\end{bmatrix} \left[\alpha \in \mathbb{R}\right]
\end{align*}
$$

Taking $\alpha = 1$, we get the eigen vector as $\mathbf{v} = \left[1 \quad 1 \quad 1\right]^T$.

As the solution obtained is only one parametric form, the geometric multiplicity of the eigenvalue 3 is 1.
In order to span the entire $\mathbb{R}^3$, we need 2 more linearly independent vectors($\mathbf{u}$ and $\mathbf{w}$). We can obtain these by using the generalized eigenvectors approach. We have: 

$$
\left(\mathbf{A}-\lambda\mathbf{I}_3\right)\mathbf{u} = \mathbf{v} \\
\implies \begin{bmatrix}
			3  & -2 & -1 \\\
			3  & -2  & -1 \\\  
			2  & -1  & -1
			\end{bmatrix}\begin{bmatrix} u_1\\\u_2\\\u_3\end{bmatrix} =\begin{bmatrix}1\\\1\\\1\end{bmatrix} 
$$

On swapping the last 2 rows and performing Row Substitutitons, we get:

$$
\begin{bmatrix} 3 &-2 & -1 \\\ 0  & 1  & -1 \\\ 0  & 0  & 0\end{bmatrix}
\begin{bmatrix} u_1\\\u_2\\\u_3\end{bmatrix} 
= \begin{bmatrix} 1\\\1\\\0\end{bmatrix} \\
\implies \mathbf{u} = \begin{bmatrix}\alpha + 1\\\ \alpha + 1\\\ \alpha \end{bmatrix} 
$$

Taking $\alpha = -1$, we get the eigen vector as $\mathbf{u} = \left[0 \quad 0 \quad -1\right]^T$.

Lastly, we have:

$$
\left(\mathbf{A}-\lambda\mathbf{I}_3\right)\mathbf{w} = \mathbf{u} \\
\implies \begin{bmatrix}3  & -2 & -1 \\\3  & -2  & -1 \\\  2  & -1  & -1\end{bmatrix}
\begin{bmatrix} w_1\\\w_2\\\w_3\end{bmatrix} = 
\begin{bmatrix} 0\\\0\\\ -1\end{bmatrix}
$$

On swapping the last 2 rows and performing Row Substitutitons, we get:

$$
\begin{bmatrix} 3  & -2 & -1 \\\ 0  & 1  & -1 \\\ 0  & 0  & 0\end{bmatrix}
\begin{bmatrix} w_1\\\w_2\\\w_3\end{bmatrix} = 
\begin{bmatrix} 0 \\\ -3 \\\0 \end{bmatrix} \\
\implies \mathbf{w} = \begin{bmatrix}\alpha - 2 \\\ \alpha - 3\\\ \alpha\end{bmatrix}
$$

Taking $\alpha = 2$, we get the eigen vector as $\mathbf{u} = \left[0 \quad -1 \quad 2\right]^T$.

Thus, the generalized eigen vectors corresponding to $\mathbf{A}$ are 

$$
\begin{bmatrix}1 \\\ 1 \\\ 1\end{bmatrix}, 
\begin{bmatrix}0 \\\ 0 \\\ -1\end{bmatrix},
\begin{bmatrix}0 \\\ -1 \\\ 2\end{bmatrix}
$$

NOTE: The values of $\alpha$ were chosen randomly in the above solution. The eigen vectors obtained will be linearly independent $\forall \alpha \in \mathbb{R}$ i.e.,  the triplet of eigen vectors obtained will always span entire $\mathbb{R}^3$. 
