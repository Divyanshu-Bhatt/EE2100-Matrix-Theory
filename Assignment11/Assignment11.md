Matrix Theory: Assignment 11 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 11. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.

## Question 2

$a)$ Since $\mathbf{A}$ and $\mathbf{B}$ are positive semi-definite matrices, they are both symmetric. Thus, for some matrices $\mathbf{U}$ and $\mathbf{V}$, we have 

$$
\mathbf{A}=\mathbf{U^T}\mathbf{U}
$$

$$
\mathbf{B}=\mathbf{V^T}\mathbf{V}
$$

$$
\mathbf{A^T}\mathbf{B}=(\mathbf{U^T}\mathbf{U})^T\mathbf{V^T}\mathbf{V}=\mathbf{U^T}\mathbf{U}\mathbf{V^T}\mathbf{V}
$$

Now, we have:

$$
\mathrm{tr}(\mathbf{A^T}\mathbf{B})=\mathrm{tr}(\mathbf{U^T}\mathbf{U}\mathbf{V^T}\mathbf{V})
$$

Since:

$$
\mathrm{tr}(\mathbf{XY})=\mathrm{tr}(\mathbf{YX})
$$

We can set $\mathbf{X}=\mathbf{U^T}$ and $\mathbf{Y}=\mathbf{UV^TV}$

Therefore, we have:

$$
\begin{align*}
\mathrm{tr}(\mathbf{A^T}\mathbf{B})&=\mathrm{tr}(\mathbf{UV^T VU^T})\\&=\mathrm{tr}(\mathbf{UV^T}(\mathbf{UV^T})^T)
\end{align*}
$$

which is of the from $\mathrm{tr}(\mathbf{M}\mathbf{M^T})$, which is always $\geq 0$.

<p align='right'>$\square$</p>

$b)$ If 

$$
\mathrm{tr}(\mathbf{A^T}\mathbf{B})=0
$$

then,

$$
\mathrm{tr}(\mathbf{UV^T}(\mathbf{UV^T})^T)=0
$$

Let $\mathbf{M}=\mathbf{U}\mathbf{V^T}$. Let the entries of $\mathbf{M}$ be $m_{ij}$. 

$$
\mathrm{tr}(\mathbf{M}\mathbf{M^T})=\sum_i \sum_j (m_{ij})^2=0
$$

$$
\begin{align*}
\implies& m_{ij}=0 \ \forall i,j\\
\implies& \mathbf{M}=0\\
\implies& \mathbf{UV^T}=0\\
\end{align*}
$$

$$
\mathbf{AB}=\mathbf{U^T UV^T V}=0
$$

<p align='right'>$\square$</p>

## Question 3

For $\mathbf{A}$ to be a positive semi-definite matrix, $\mathbf{x^T Ax} \ge 0\  \forall \mathbf{x} \ \in \mathbb{R}^n$.

Now we know that,

$$
\begin{align*}
\mathbf{x}^T \mathbf{Ax} &= \sum_{ij} x_i x_j A_{ij}  \\
&= \sum_{ij} (\mathbf{xx^T}) _ {ij} A_{ij}
\end{align*}
$$

Now for any two matrices $\mathbf{A}$ and $\mathbf{B}$, the trace of $\mathbf{C = A^TB}$ is given by

$$
\mathrm{tr}\mathbf{(C)} = \sum_i c_{ii}\\
$$

We can write $c_{ii}$ as the dot product of the $i^{th}$ row of $\mathbf{A}$ and the $i^{th}$ column of $\mathbf{B}$

$$
\begin{align*}
\mathrm{tr}(\mathbf{C})&=\sum_i \left(\sum_{j} A_{ij} B_{ji}\right)\\
&=\sum_{ij} A_{ij} B_{ij} \\
\end{align*}
$$

Combining the above two equations, we get

$$
\begin{align*}
\mathbf{x}^T \mathbf{Ax} &= \sum_{ij} x_i x_j A_{ij}  \\ 
&= \sum_{ij} A_{ij} \mathbf{(xx^T)}_{ij} \\
&= \mathrm{tr}\mathbf{(A^T xx^T)} \ge 0
\end{align*}
$$


As $\mathbf{B}$ is also a positive semi-definite matrix, we can write it as 

$$
\mathbf{B} = \sum_{i} \sigma_i \mathbf{v_i v_i^T}
$$

Using the above equation we can write,

$$
\begin{align*}
\mathrm{tr}(\mathbf{A^TB}) &= \mathrm{tr}\left(\mathbf{A^T}\sum_{i} \sigma_i \mathbf{v_i v_i^T}\right) \\
&= \sum_{i} \underbrace{\sigma_i}_ {\ge 0} \underbrace{\mathrm{tr}\left(\mathbf{A^Tv_i v_i^T}\right)}_{\ge 0} \\
&\ge 0
\end{align*}
$$

<p align='right'>$\square$</p>
