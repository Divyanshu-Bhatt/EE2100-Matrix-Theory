Matrix Theory Assignment 2 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 2. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case of any discrepancy you find in the solutions provided.

## Question 1
$a)$ 
**NO**, the vector space $\mathbb{R}^2$ cannot have a basis $B = \set{\mathbf b_1, \mathbf b_2} \in \mathbb{C^2}$. 
Note the difference between a subset of a set and the subspace of a vector space. 

$$
\begin{gather}
\mathbb{R}^2 \subset \mathbb{C}^2 \\
\mathbb{R}^2 \  \text{is $\mathbf{NOT}$ always a subspace of} \ \mathbb{C}^2 \\
\end{gather}
$$ 

Here $\mathbb R^2$ is not a subspace of $\mathbb C^2$ since the field over which this vector space is defined is $\mathbb C$.

If $\mathbb{W}$ is a subspace of the vector space $\mathbb{V}$, it must satisfy the following property

$$
\begin{gather}
\alpha_1 \mathbf x+\alpha_2  \mathbf y \in \mathbb{W} \qquad \forall\mathbf x, \mathbf y \in \mathbb{W},\ \alpha_1,\alpha_2 \in \mathbb{F}
\end{gather}
$$ 

where $\mathbb{F}$ is the field over which the vector space is defined.

For this question, $\alpha_1,\alpha_2 \in \mathbb C$. If $\mathbf x,\mathbf y$ belong to $\mathbb{R}^2$, then $\alpha_1 \mathbf x+ \alpha_2  \mathbf y$ must also belong to $\mathbb{R}^2$. But, since $\alpha_1$ and $\alpha_2\in \mathbb{C}$ there exists $\alpha_1,\alpha_2$ such that $\alpha_1 \mathbf x +\alpha_2 \mathbf y \in \mathbb C^2$. This proves that $\mathbb{R}^2$ is not the required subspace.

Had the field been $\mathbb{R}$, $\mathbb{R}^2$  would have indeed been a subspace of $\mathbb{C}^2$. However, as the field is $\mathbb{C}$, it is not a subspace since the rules of linear combination fail to hold as shown above.  

Just because you are able to generate all the vectors whose entries are purely real, doesn't mean that the generated vector belongs to the real space. 

$b)$ The strict condition on $\alpha_1$ and $\alpha_2$ is that they must be complex to generate every vector in $\mathbb{R}^2$. 

Let, 

$$
\mathbf b_1 = \begin{bmatrix}b_{11} \newline b_{21}\end{bmatrix} \quad \mathbf {b_2}=\begin{bmatrix}b_{21} \newline b_{22}\end{bmatrix}
$$

where $b_{ij}\in \mathbb{C} \ \forall i,j\in \{1,2\}$. Now, we have $\alpha_1 b_{11}+ \alpha_2 b_{21} \in \mathbb{R}$ and $\alpha_1 b_{21}+ \alpha_2 b_{22} \in \mathbb{R}$. For this to hold, $\alpha_1, \alpha_2 \in \mathbb{C}$. 

Remember, even if you choose $\mathbf{b_1}=[1 \ 0]^T$ and $\mathbf{b_2}=[0 \ 1]^T$, the elements are still from the field $\mathbb{C}$. The elements can be written as $1 + 0j$ where $j$ is the imaginary unit.

$c)$ An example would be the basis $B = \set{\mathbf b_1, \mathbf b_2}$, such that $\mathbf{b_1}=[1 \ 0]^T$ and $\mathbf{b_2}=[0 \ 1]^T$. 

Expression for computing the coordinate vector $\mathbf{x}= [x_1 \ x_2]^T$ is 

$$
\begin{bmatrix}x_1 \newline x_2\end{bmatrix} = x_1\mathbf b_1 + x_2\mathbf b_2
$$

$d)$ There exists **NO** complex basis of $\mathbb{R}^2$ (following from part (a)) that constitutes an orthogonal basis. But, in order to generate vectors of dimension $2$, one needs to have an orthogonal complex basis. 

## Question 2 
$a)$ According to property of norm, 

$$
\begin{align*}
\lVert f(x)\rVert_2 &= \sqrt{f(x)\cdot f(x)} \\
&=\sqrt{\int_{-\infty}^{\infty}{{f(x)}^2}dx}
\end{align*}
$$

We know that:

$$
\begin{align*}
\ f(x)^2 & > 0 \quad \forall x\neq 0\\
\implies \int_{-\infty}^{\infty}{{f(x)}^2}dx &> 0 \\
\implies\sqrt{\int_{-\infty}^{\infty}{{f(x)}^2}dx} &> 0 \\
\implies\text{i.e.  } \|f(x)\|_2 &> 0
\end{align*}
$$

Now, coming to the scalability property of norm:

$$
\begin{align*}
\lVert cf(x)\rVert_2 &= \sqrt{\int_{-\infty}^{\infty}{(\text{c}{f(x)})^2}dx} \\
&= \sqrt{\int_{-\infty}^{\infty}{c^2{f(x)}^2}dx} \\
&= \sqrt {c^2{\int_{-\infty}^{\infty}{{f(x)}^2}}dx} \\
&= |c| \sqrt {{\int_{-\infty}^{\infty}{{f(x)}^2}}dx} \\
&= |c| \|f(x)\|_2
\end{align*}
$$



Proving the triangle inequality, let $f(x)$ and $g(x)$ be two independent functions:

Firstly we have to prove the cauchy-schwarz inequality:

$$
\begin{align*}
\langle f(x) - a g(x) ,  f(x) - a g(x) \rangle &= \langle f(x), f(x) \rangle - a \langle f(x), g(x) \rangle - a \langle g(x), f(x) \rangle + a^2 \langle g(x), g(x) \rangle \\
&= \lVert f(x)\rVert_2^2 - a \langle f(x), g(x) \rangle - a \langle g(x), f(x) \rangle + a^2 \lVert g(x)\rVert_2^2 \\
\end{align*}
$$

Let $a = \displaystyle \frac{\langle f(x), g(x) \rangle}{\lVert g(x)\rVert_2^2} $

$$
\begin{align*}
\langle f(x) - a g(x) ,  f(x) - a g(x) \rangle &= \lVert f(x)\rVert_2^2 - \frac{\langle f(x), g(x) \rangle}{\lVert g(x)\rVert_2^2} \langle f(x), g(x) \rangle - \frac{\langle f(x), g(x) \rangle}{\lVert g(x)\rVert_2^2} \langle g(x), f(x) \rangle + \frac{\langle f(x), g(x) \rangle^2}{\lVert g(x)\rVert_2^2} \\
&= \lVert f(x)\rVert_2^2 - \frac{\langle f(x), g(x) \rangle^2}{\lVert g(x)\rVert_2^2} \\ 
&\ge \lVert f(x)\rVert_2^2 - \frac{\lVert f(x)\rVert^2_2 \lVert g(x) \rVert^2_2}{\lVert g(x)\rVert_2^2} \tag{Cauchy Schwarz Inequality} \\
&\ge 0
\end{align*}
$$

$$
\begin{align*}
\implies \lVert f(x)\rVert_2^2{\lVert g(x)\rVert_2^2}  &\ge \langle f(x), g(x) \rangle^2\\
\implies \lVert f(x)\rVert_2{\lVert g(x)\rVert_2}  &\ge \langle f(x), g(x) \rangle\\
\end{align*}
$$

Now, we can prove the triangle inequality:

$$
\begin{align*}
\lVert f(x)+g(x)\rVert_2^2 &= {(f(x)+g(x))\cdot(f(x)+g(x))} \\
&= {\int_{-\infty}^{\infty}{(f(x)+g(x))^2} dx} \\
&= {\int_{-\infty}^{\infty}({f(x)^2 + g(x)^2 + 2 f(x) g(x)}) dx}\\
&= \lVert f(x)\rVert_2^2 + \lVert g(x)\rVert_2^2 + 2\int_{-\infty}^{\infty}{f(x) g(x)} dx \\
&= \lVert f(x)\rVert_2^2 + \lVert g(x)\rVert_2^2 + 2\langle f(x), g(x) \rangle\\
&\le \lVert f(x)\rVert_2^2 + \lVert g(x)\rVert_2^2 + 2\lVert f(x)\rVert_2{\lVert g(x)\rVert_2} \\
&= (\lVert f(x)\rVert_2 + \lVert g(x)\rVert_2)^2 \\
\implies \lVert f(x)+g(x)\rVert_2 &\le \lVert f(x)\rVert_2 + \lVert g(x)\rVert_2
\end{align*}
$$

$b)$ Consider the inner product of the two functions:

$$
\begin{align*}
\int_{-\infty}^{\infty}{\sin(mx)\cos(nx)} dx &= \frac{1}{2}\int_{-2\pi}^{2\pi}{\sin((m+n)x) + \sin((m-n)x)}\space dx \\
&= \frac{1}{2}\int_{-2\pi}^{2\pi}{\sin((m+n)x)} dx + \frac{1}{2}\int_{-2\pi}^{2\pi}{\sin((m-n)x)} dx \\
&= 0 
\end{align*}
$$

because $\sin((m+n)x$) and $\sin((m-n)x)$ are odd functions and the limits of the integral is symmetric about $0$, hence the integral evaluates to $0$.

$c)$ Let $f(x) = 1 \in [a, b]$. If there exists a $g(x) \in [a, b]$ that is orthogonal to $f(x)$ then

$$
\begin{align*}
\int_{a}^{b}{f(x)g(x)}\space dx &= 0 \\
\int_{a}^{b}{g(x)}\space dx &= 0 \\
\end{align*}
$$

This is possible for various functions. Hence, there is a set of functions that is orthogonal to $f(x)$.

## Question 3
We have been given that $\mathbf u_1$ and $\mathbf u_2$ are two linearly independent vectors in $\mathbb{R}^2$. Further, $\mathbf b_1 = 2\mathbf u_1 + 3\mathbf u_2$ and  $\mathbf b_2 = 4\mathbf u_1+5\mathbf u_2.$

Now, we need to prove or disprove that $B = \{\mathbf b_1,\mathbf b_2\}$ constitute the basis for $\mathbb{R}^2$.

Let us try to prove that the $B$ constitutes the basis. If we reach a contradiction, we can be sure that $B$ does not constitute the basis for $\mathbb{R}^2$.

We know that for a set of vectors to constitute a basis, it must satisfy two conditions: 
1. The vectors must be linearly independent.
2. The vectors must span the entire subspace \($\mathbb{R}^2$ in our case\).
   
To prove linear independence, let $\alpha_1 \text{ and } \alpha_2$ be two variables such that: 

$$
\begin{align*}
\alpha_1\mathbf b_1 + \alpha_2 \mathbf b_2 &= 0 \\
\alpha_1\space (2\mathbf u_1 + 3\mathbf u_2) + \alpha_2\space (4\mathbf u_1+5\mathbf u_2) &= 0 \\
(2\alpha_1+4\alpha_2)\mathbf u_1 + (3\alpha_1+5\alpha_2)\mathbf u_2 &= 0 \\
\end{align*}
$$

Since $\mathbf u_1$ and $\mathbf u_2$ are linearly independent, this is possible only when both the coefficients are zero. 

$$
\begin{align*}
2\alpha_1+4\alpha_2 = 0 \qquad 3\alpha_1+5\alpha_2=0\space\\
\end{align*}
$$

On solving this pair of equations, we get one unique solution $\alpha_1=0$ and $\alpha_2=0.$ Hence, we can say that $\mathbf b_1$ and $\mathbf b_2$ are linearly independent. 

Now, we know that, for any m linearly independent vectors, they span the entirety of $\mathbb{R}^2$. Thus, $\mathbf u_1$ and $\mathbf u_2$ span the entire subspace $\mathbb{R}^2$.

**An alternate method to prove that the vector spans the entire subspace:**  

Let a vector $\mathbf v = \gamma \mathbf u_1 + \nu\mathbf  u_2$, where $\gamma$ and $\nu$ are some constants. Also, $\mathbf v=\alpha_1\space \mathbf b_1 + \alpha_2 \space \mathbf b_2$, where $\alpha_1$ and $\alpha_2$ are constants.

$$
\begin{align*}
\mathbf v&=\alpha_1\mathbf b_1 + \alpha_2  \mathbf b_2 \\
&=\alpha_1(2\mathbf u_1 + 3\mathbf u_2) + \alpha_2(4\mathbf u_1+5\mathbf u_2) \\
&=(2\alpha_1+4\alpha_2)\mathbf  u_1 + (3\alpha_1+5\alpha_2)\mathbf  u_2 \\
\end{align*}
$$

Thus, we get $\gamma=2\alpha_1+4\alpha_2$ and  $\nu=3\alpha_1+5\alpha_2$ 
We check if this set of equations has a unique solution or not. For the solution to be unique, the determinant has to be non-zero.

$$
\begin{align*}
\Delta &= \begin{vmatrix} 2 & 4 \newline 3 & 5 \end{vmatrix} \\
&= (2\times5) \space-\space(3\times4) \\
&=-2\\
&\neq0
\end{align*}
$$

The solution is unique. This proves that $B = \set{\mathbf b_1,\mathbf b_2}$ constitute the basis for $\mathbb{R}^2$.
