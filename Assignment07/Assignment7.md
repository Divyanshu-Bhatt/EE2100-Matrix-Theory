Matrix Theory: Assignment 7 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 7. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.

## Question 2
We have $m$ systems of, say, $n$ equations each. We can represent this as:

$$
\mathbf{A}\mathbf{x}_i = \mathbf{b}_i \quad \forall i \in \set{1,2,\cdots,m}
$$

where $\mathbf{A}\in \mathbb{R}^{n\times n}$ and $\mathbf{x}_i, \mathbf{b}_i \in \mathbb{R}^{n} \forall i \in \set{1,\cdots,m}$ i.e. only $a$ and $b$ change for each system.

$a)$ Using Gaussian elimination involves the following steps:
- Creation and echelonisation of the augmented matrix
	- Forward elimination for the $i^{th}$ row involves $n-i-1$ row subtractions. Each row subtraction takes $\mathcal{O}(n)$ time. Thus, forward elimination takes $\mathcal{O}(n^2)$ time. 
	- We need to perform these row subtractions for all the equations in the system. Thus, forward elimination takes $\mathcal{O}(n^3)$ time.
	- We need to perform the above for all the $m$ systems. Thus, forward elimination takes $\mathcal{O}(mn^3)$ time.
- Back Substitution
	- For the $i^{th}$ row we need to perform $\mathcal O(i)$ operations. Thus, back substitution takes $\mathcal{O}(n^2)$ time. We have to perform this for all the $m$ systems. Thus, back substitution takes $\mathcal{O}(mn^2)$ time.

Thus, the total time complexity of Gaussian elimination is $\mathcal{O}(mn^2)$ + $\mathcal{O}(mn^3)$ = $\mathcal{O}(mn^3)$.

$b)$ Using LU Decomposition involves the following steps:
- LU Decomposition
	- We need to perform the LU Decomposition only one time as the matrix $\mathbf{A}$ doesn't change. Thus, LU Decomposition takes $\mathcal{O}(n^3)$ time.
- Calculating $\mathbf{L}^{-1}$
	- We need to compute the matrix inverse only once as the matrix $\mathbf{L}$ doesn't change. Thus, calculating $\mathbf{L}^{-1}$ takes $\mathcal{O}(n^3)$ time.
- Calculating $\mathbf{L}^{-1}\mathbf{x}$ (matrix vector product) 
	- For multiplying a matrix and a vector, we need to perform $n$ dot products. Each dot product takes $\mathcal{O}(n)$ time. Thus, the matrix vector product takes $\mathcal{O}(n^2)$ time.
- Forward substitution
	- Forward substitution is same as the backward substitution in Gaussian elimination. Thus, forward substitution takes $\mathcal{O}(n^2)$ time. We need to perform this every time for the $m$ systems. Thus, forward substitution takes $\mathcal{O}(mn^2)$ time.

Thus, the total time complexity of LU Decomposition is $\mathcal{O}(n^3) + \mathcal{O}(n^3) + \mathcal{O}(mn^2) = \mathcal{O}(mn^2)$. Here, we want to analyze the complexity for solving $m$ systems. Hence, one can consider that $m \gg n$. 

## Question 3

Consider the given system of linear equations:

$$
\begin{bmatrix} 1 & 2 & 2 & 1 \\\ 2 & 1 & 1 & 2 \\\ 2 & 1 & 2 & 1 \\\ 1 & 2 & 1 & 2\end{bmatrix} \begin{bmatrix} x_1 \\\ x_2 \\\ x_3 \\\ x_4\end{bmatrix} = \begin{bmatrix} 1 \\\ 1 \\\ 1 \\\ 1\end{bmatrix} 
$$

$a)$ We start by performing an $\mathbf{LU}$ Decomposition on matrix $\mathbf{A}$

$$
\begin{align*}
\left(\mathbf{L} _ p \right) _ {i,i} &= \begin{cases}1 & i \in \{1,2, \cdots ,p \}\\
        \left(\mathbf{A} _ {p-1}\right) _ {p,p} &  \text{otherwise}
    \end{cases}\\
\left(\mathbf{L} _ p\right) _ {i,j} &= 
    \begin{cases}
        -\left(\mathbf{A} _ {p-1}\right) _ {i,j} & \ j = p \  \text{and} \ i > j\\
        0 & \text{otherwise}\\
    \end{cases}
\end{align*} 
$$

$$
\begin{align*}
\mathbf{L}_1 &= \begin{bmatrix} 1 & 0 & 0 & 0 \\\ -2 & 1 & 0 & 0 \\\ -2 & 0 & 1 & 0 \\\ -1 & 0 & 0 & 1 \\\ \end{bmatrix} \\
\implies \mathbf{A}_1 &= \mathbf{L}_1\mathbf{A} = \begin{bmatrix} 1 & 2 & 2 & 1 \\\ 0 & -3 & -3 & 0 \\\ 0 & -3 & -2 & -1 \\\ 0 & 0 & -1 & 1\end{bmatrix}
\end{align*}
$$

$$
\begin{align*}
\mathbf{L}_2 &= \begin{bmatrix} 1 & 0 & 0 & 0 \\\ 0 & 1 & 0 & 0 \\\ 0 & 3 & -3 & 0 \\\ 0 & 0 & 0 & -3 \end{bmatrix} \\
\implies \mathbf{A}_2 &= \mathbf{L}_2\mathbf{A}_1 = \begin{bmatrix} 1 & 2 & 2 & 1 \\\ 0 & -3 & -3 & 0 \\\ 0 & 0 & -3 & 3 \\\ 0 & 0 & 3 & -3 \\\ \end{bmatrix} 
\end{align*}
$$

$$
\begin{align*}
\mathbf{L}_3 &= \begin{bmatrix} 1 & 0 & 0 & 0 \\\ 0 & 1 & 0 & 0 \\\ 0 & 0 & 1 & 0 \\\ 0 & 0 & -3 & -3\end{bmatrix} \\
\implies \mathbf{A}_3 &= \mathbf{L}_3\mathbf{A}_2 = \begin{bmatrix} 1 & 2 & 2 & 1 \\\ 0 & -3 & -3 & 0 \\\ 0 & 0 & -3 & 3 \\\ 0 & 0 & 0 & 0\end{bmatrix}
\end{align*}
$$

$$
\begin{align*}
\mathbf{U} &= \mathbf{A}_3 = \mathbf{L}_3\mathbf{L}_2\mathbf{L}_1\mathbf{A} = \mathbf{L}^{-1} \mathbf{A}\\
\implies \mathbf{U} &= \begin{bmatrix} 1 & 2 & 2 & 1 \\\ 0 & -3 & -3 & 0 \\\ 0 & 0 & -3 & 3 \\\ 0 & 0 & 0 & 0 \\ \end{bmatrix}
\end{align*}
$$

$$
\mathbf{L}^{-1} = \mathbf{L}_3\mathbf{L}_2\mathbf{L}_1  = \begin{bmatrix} 1 & 0 & 0 & 0 \\\ 0 & 1 & 0 & 0 \\\ 0 & 0 & 1 & 0 \\\ 0 & 0 & -3 & -3\end{bmatrix}\begin{bmatrix} 1 & 0 & 0 & 0 \\\ 0 & 1 & 0 & 0 \\\ 0 & 3 & -3 & 0 \\\ 0 & 0 & 0 & -3 \\\ \end{bmatrix}\begin{bmatrix} 1 & 0 & 0 & 0 \\\ -2 & 1 & 0 & 0 \\\ -2 & 0 & 1 & 0 \\\ -1 & 0 & 0 & 1\end{bmatrix}
$$

$$
\implies \mathbf{L}^{-1} = \begin{bmatrix} 1 & 0 & 0 & 0 \\\ -2 & 1 & 0 & 0 \\\ 0 & 3 & -3 & 0 \\\ -9 & -9 &  9 &  9\end{bmatrix}
$$

$$
\implies \mathbf{L} = \mathbf{L}_1^{-1}\mathbf{L}_2^{-1}\mathbf{L}_3^{-1}
$$

$$
\begin{align*}
\left(\mathbf{L^{-1}} _ p\right) _ {i,i} &= 
    \begin{cases}
        1 &  i \in \{1,2, \cdots ,p \}\\
        1\over \left(\mathbf{A} _ {p-1}\right) _ {p,p} & \text{otherwise}
    \end{cases}\\
\left(\mathbf{L} _ p^{-1}\right) _ {i,j} &= 
    \begin{cases}
        {\left(\mathbf{A} _ {p-1}\right) _ {i,j}\over\left(\mathbf{A} _ {p-1}\right)_{j,j}} &  j = p \  \text{and}  \ i > j\\
        0 & \text{otherwise}\\
    \end{cases}
\end{align*} 
$$

$$
\implies \mathbf{L} = \mathbf{L}_1^{-1}\mathbf{L}_2^{-1}\mathbf{L}_3^{-1} = \begin{bmatrix} 1 & 0 & 0 & 0 \\\ 2 & 1 & 0 & 0 \\\ 2 & 0 & 1 & 0 \\\ 1 & 0 & 0 & 1\end{bmatrix}\begin{bmatrix} 1 & 0 & 0 & 0 \\\ 0 & 1 & 0 & 0 \\\ 0 & 1 & -{1\over3} & 0 \\\ 1 & 0 & 0 & -{1\over3} \\\ \end{bmatrix}\begin{bmatrix} 1 & 0 & 0 & 0 \\\ 0 & 1 & 0 & 0 \\\ 0 & 0 & 1 & 0 \\\ 0 & 0 & -1 & -{1\over 3}\end{bmatrix} \\
$$

$$
\implies \mathbf{L} = \begin{bmatrix} 1 & 0 & 0 & 0 \\\ 2 & 1 & 0 & 0 \\\ 2 & 1 & -{1\over 3} & 0 \\\ 1 & 0 & 1\over 3 & 1\over 9\end{bmatrix} 
$$

NOTE: The LU Decomposition performed is based off the generalised expression used while computing $\mathbf{L}_p$. This is not the only method that can be used to compute $\mathbf{L}$ and $\mathbf{U}$. Another standardised method gives the following results:

$$
\begin{align*}
\mathbf{L} &= \begin{bmatrix} 1 & 0 & 0 & 0 \\\ 2 & 1 & 0 & 0 \\\ 2 & 1 & 1 & 0 \\\ 1 & 0 & -1 & 1\end{bmatrix} \\
\mathbf{U} &= \begin{bmatrix} 1 & 2 & 2 & 1 \\\ 0 & -3 & -3 & 0 \\\ 0 & 0 & 1 & -1 \\\ 0 & 0 & 0 & 0\end{bmatrix} \\
\end{align*}
$$

Based upon the result used, the solution to the other parts may vary. However, the solution to the system of linear equations will remain the same.

$b)$ We now compute the solution to the system of linear equations.

We have $\mathbf{A} = \mathbf{LU}$ and $\mathbf{A}\mathbf{x} = \mathbf{b}$, so:

$$
\begin{align*}
\mathbf{LUx} &= \mathbf{b} \\
\implies \mathbf{Ux} &= \mathbf{L}^{-1}\mathbf{b} \\
\implies \begin{bmatrix} 1 & 2 & 2 & 1 \\\ 0 & -3 & -3 & 0 \\\ 0 & 0 & -3 & 3 \\\ 0 & 0 & 0 & 0\end{bmatrix}\begin{bmatrix} x_1 \\\ x_2 \\\ x_3 \\\ x_4\end{bmatrix} &= \begin{bmatrix} 1 & 0 & 0 & 0 \\\ -2 & 1 & 0 & 0 \\\ 0 & 3 & -3 & 0 \\\ -9 & -9 &  9 &  9\end{bmatrix}\begin{bmatrix} 1 \\\ 1 \\\ 1 \\\ 1\end{bmatrix}\\
\implies \begin{bmatrix} 1 & 2 & 2 & 1 \\\ 0 & -3 & -3 & 0 \\\ 0 & 0 & -3 & 3 \\\ 0 & 0 & 0 & 0\end{bmatrix}\begin{bmatrix} x_1 \\\ x_2 \\\ x_3 \\\ x_4\end{bmatrix} &= \begin{bmatrix} 1 \\\ -1 \\\ 0 \\\ 0\end{bmatrix}
\end{align*}
$$

On performing Back Substitution, we see that the last equation results in infinite solutions. We find the solution in parametric form i.e., let $x_4 = \alpha$

$$
\begin{align*}
 -3 x_3 + 3&\alpha = 0 \\
\implies x_3 &= \alpha 
\end{align*}
$$

$$
\begin{align*}
-3x_2-3&x_3 = -1 \\
\implies x_2 &= {1\over3} - \alpha
\end{align*}
$$

$$
\begin{align*}
x_1 + 2x_2 + &2x_3 + x_4 = 1 \\
\implies x_1 &= {1\over3} - \alpha \\
\end{align*} 
$$

$$
\implies \mathbf{x} =  \begin{bmatrix} {1\over3} - \alpha & {1\over3} - \alpha & \alpha & \alpha \end{bmatrix}^T
$$

$c)$ We now compute the solution to the system of linear equations by replacing $\mathbf{b}$ with $\mathbf{z}$ 

We have $\mathbf{A} = \mathbf{LU}$ and $\mathbf{A}\mathbf{x} = \mathbf{z}$, so:

$$
\begin{align*}
\mathbf{LUx} &= \mathbf{z} \\
\implies \mathbf{Ux} &= \mathbf{L}^{-1}\mathbf{z} \\
\implies \begin{bmatrix} 1 & 2 & 2 & 1 \\\ 0 & -3 & -3 & 0 \\\ 0 & 0 & -3 & 3 \\\ 0 & 0 & 0 & 0\end{bmatrix}\begin{bmatrix} x_1 \\\ x_2 \\\ x_3 \\\ x_4\end{bmatrix} &= \begin{bmatrix} 1 & 0 & 0 & 0 \\\ -2 & 1 & 0 & 0 \\\ 0 & 3 & -3 & 0 \\\ -9 & -9 &  9 & 9 \end{bmatrix}\begin{bmatrix} 1 \\\ 2 \\\ 3 \\\ 4\end{bmatrix}\\
\implies \begin{bmatrix} 1 & 2 & 2 & 1 \\\ 0 & -3 & -3 & 0 \\\ 0 & 0 & -3 & 3 \\\ 0 & 0 & 0 & 0\end{bmatrix}\begin{bmatrix} x_1 \\\ x_2 \\\ x_3 \\\ x_4\end{bmatrix} &= \begin{bmatrix} 1 \\\ 0 \\\ -3 \\\ 36\end{bmatrix}
\end{align*}
$$

Now perform Back Substitution. As the last equation has no solution, we can conclude that no solution exists.

## Question 4
The given matrix is positive definite. THus, we can perform a Cholesky Decomposition. We will solve this via LU decomposition first:

$$
\mathbf{M}=\begin{bmatrix}
			6  & 15 & 55 \\
			15  & 55  & 225 \\  
			55  & 225  & 979 \\
			\end{bmatrix}
$$

$$
\text{Step1:} \ R_2=R_2-(5/2)R_1
$$

$$
\mathbf{M_1}=\begin{bmatrix}
			6  & 15 & 55 \\
			0  & 35/2  & 175/2 \\  
			55  & 225  & 979 \\
			\end{bmatrix}
$$


$$
\text{Step2:} \ R_3=R_3-(55/6)R_1
$$

$$
\mathbf{M_2}=\begin{bmatrix}
			6  & 15 & 55 \\
			0  & 35/2  & 175/2 \\  
			0  & 525/6  & 2849/6 \\
			\end{bmatrix}
$$

$$
\text{Step3:} \ R_3=R_3-5R_2
$$

$$
\mathbf{M_3}=\begin{bmatrix}
			6  & 15 & 55 \\
			0  & 35/2  & 175/2 \\  
			0  & 0  & 112/3 \\
			\end{bmatrix}=\mathbf{U}
$$

We can use the subtraction coefficients to find $\mathbf{L}$. 

We consider the matrix 

$$
\mathbf{I}=\begin{bmatrix}
			1  & 0 & 0 \\
			0  & 1  & 0 \\  
			0  & 0  & 1 \\
			\end{bmatrix}
$$

and fill the entries $\mathbf{I} _ {21},\mathbf{I} _ {31},\mathbf{I}_{32}$ with $(5/2), (55/6)$, and $5$ respectively. This gives us $\mathbf{L}$.

$$
\mathbf{L}=\begin{bmatrix}1  & 0 & 0 \\\ 5/2  & 1  & 0 \\\ 55/6  & 5  & 1\end{bmatrix}
$$

It might not be immediately apparent that $\mathbf{L}=\mathbf{U}^T$. This is simply beacuse of the method used to calculate the $\mathbf{LU}$ decomposition. If the identity matrix is used to fill the entries of $\mathbf{L}$, then barring some special cases, we won't get the required result. Instead, let's try to algebraically solve for the values: 

$$
\begin{align*}
\mathbf{L}&=\begin{bmatrix}a_{11}  & 0 & 0 \\ a_{21}  & a_{22}  & 0 \\ a_{31}  & a_{32}  & a_{33}\end{bmatrix}\\
\implies \mathbf{U}&=\begin{bmatrix}a_{11}  & a_{21} & a_{31} \\\ 0  & a_{22}  & a_{32} \\\ 0  & 0  & a_{33}\end{bmatrix}
\end{align*}
$$

$$
\implies \mathbf{LU}=\begin{bmatrix}a_{11}^2  & a_{11}a_{21} & a_{11}a_{31} \\\ a_{21}a_{11}  & a_{21}^2+a_{22}^2  & a_{21}a_{31}+a_{22}a_{32} \\\ a_{31}a_{11}  & a_{31}a_{21}+a_{32}a_{22}   & a_{31}^2+a_{32}^2+a_{33}^2\end{bmatrix}
$$

On comparing and solving, we get:

$$
\mathbf{M}=\begin{bmatrix}\sqrt{6}  & 0 & 0 \\\ 15/\sqrt{6}  & \sqrt{105/6} & 0 \\\ 55/\sqrt{6} & \sqrt{2625/6} & \sqrt{112/3} \end{bmatrix}\begin{bmatrix}\sqrt{6}  & 15\sqrt{6} & 55\sqrt{6}\\\ 0 & \sqrt{105/6} & \sqrt{2625/6} \\\ 0 & 0 & \sqrt{112/3}\end{bmatrix}
$$

Could we have reached this conclusion from the $\mathbf{LU}$ decomposition itself? Yes, using the standard method for $\mathbf{LU}$ decomposition, if we perform the following operations, we get the required result.

$$
\begin{gather*}
\mathbf{L} _ {11} ^ {\text{new}} = \mathbf{U} _ {11} ^ {\text{new}} = \sqrt{U_{11}} \\
\mathbf{L} _ {22} ^ {\text{new}} = \mathbf{U} _ {22} ^ {\text{new}} = \sqrt{U_{22}} \\
\mathbf{L} _ {33} ^ {\text{new}} = \mathbf{U} _ {33} ^ {\text{new}} = \sqrt{U_{33}} \\
\mathbf{L} _ {12} ^ {\text{new}} = \mathbf{U} _ {21} ^ {\text{new}} = \sqrt{U_{11}}{L_{12}} = \frac{{U_{21}}}{\sqrt{U_{11}}} \\
\mathbf{L} _ {13} ^ {\text{new}} = \mathbf{U} _ {31} ^ {\text{new}} = \sqrt{U_{11}}{L_{13}} = \frac{U_{31}}{\sqrt{U_{11}}} \\
\mathbf{L} _ {32} ^ {\text{new}} = \mathbf{U} _ {23} ^ {\text{new}} = \sqrt{L_{23}U_{32}}
\end{gather*}
$$

Food for thought...how to extend this idea for $n \times n$ matrices?
