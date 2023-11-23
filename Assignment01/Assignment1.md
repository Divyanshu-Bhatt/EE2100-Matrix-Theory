Matrix Theory Assignment 1 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 1. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case of any discrepancy you find in the solutions provided.



## Question 1
Given $\mathbf{x} \in \mathbb{R^N}$  Let $\mathbf{x} = [x_1 \ x_2 \ \cdots \ x_N]^T$

$a)$ Average, $\displaystyle\mu=\frac{1}{N}\sum_{n=1}^{N} x_{n}$  Since, the daily "price" of a stock can never be negative:  $\ |x_{n}|=x_{n}$ 

$$
\begin{align*}
\mu&=\frac{1}{N}\sum_{n=1}^{N} |x_{n}| \\
\implies \mu&=  \frac{1}{N} \lVert\textbf{x}\rVert_{1}
\end{align*}
$$ 

$b)$ We calculate the variance as follows:

$$
\begin{align*}
\sigma^2 &= \frac{1}{N} \sum_{n=1}^{N} (x_{n}-\mu)^2 \\
&= \frac{1}{N} \sum_{n=1}^{N} (x_{n}^2-2x_{n}\mu+\mu^2) \\
&= \frac{1}{N}\left(\sum_{n=1}^{N} x_{n}^2-\sum_{n=1}^{N}2x_{n}\mu+\sum_{n=1}^{N}\mu^2\right)
\end{align*}
$$

As we know that , $|x_{n}^2|=x_{n}^2$

$$
\begin{align*}
\implies \sigma^2 &= \frac{1}{N} \left(\sum_{n=1}^{N} |x_{n}|^2 -\mu\sum_{n=1}^{N}2x_{n}+N\mu^2\right)\\
&= \frac{1}{N}\left(\lVert\textbf{x}\rVert_{2}^2-2\mu\lVert\textbf{x}\rVert_{1} +N.\frac{1}{N^2}\lVert\textbf{x}\rVert_{1}^2\right) \\
&= \frac{1}{N}\left(\lVert\textbf{x}\rVert_{2}^2-\frac{2}{N}\lVert\textbf{x}\rVert_{1}^2+\frac{1}{N}\lVert\textbf{x}\rVert_{1}^2\right)\\
&=\frac{1}{N}\lVert\textbf{x}\rVert_{2}^2 - \frac{1}{N^2}\lVert\textbf{x}\rVert_{1}^2
\end{align*}
$$

$c)$ We now find a recursive relation for $\mu$ as 

$$
\begin{align*}
\mu_{N+1}&=\frac{1}{N+1}\sum_{n=1}^{N+1} x_{n}\\
&=\frac{1}{N+1}\left(\left(\sum_{n=1}^{N} x_{n}\right)+x_{n+1}\right)\\
&=\frac{1}{N+1}(N\mu_{N}+x_{n+1})
\end{align*}
$$

$d)$ We now find a recursive relation for $\sigma^2$ as

$$
\begin{align*}
 \sigma^2_{N+1} &= \frac{1}{N+1} \sum_{n=1}^{N+1}\left(x_{n}-\mu_{N+1}\right)^2  \\
&=\frac{1}{N+1} \sum_{n=1}^{N+1} \left(x_{n}^2-2\mu_{N+1} x_{n}+\mu_{N+1}^2\right) \\
&=\frac{1}{N+1}(N\sigma^2_{N}+N\mu_{N}^2+x_{n+1}^2)-2\mu_{N+1}^2+\mu_{N+1}^2\\
&=\frac{N}{N+1}\sigma^2_{N}+\frac{N}{N+1}\mu_{N}^2+\frac{1}{N+1}x_{n+1}^2-\mu_{N+1}^2\\
&=\frac{N}{N+1}\sigma^2_{N}+\frac{N}{N+1}\mu_{N}^2+\frac{1}{N+1}x_{n+1}^2-\left(\frac{1}{N+1}\right)^2(N\mu_{N}+x_{n+1})^2\\
&=\frac{1}{N+1}\left(N\sigma^2_{N}+N\mu_{N}^2+x_{n+1}^2-\frac{1}{N+1}(N^2\mu_{N}^2+2N\mu_{N}x_{n+1}+x_{n+1}^2)\right)\\
&=\frac{N}{N+1}\left(\sigma^2_{N}+\frac{1}{N+1}(\mu_{N}-x_{n+1})^2\right)\\
\end{align*}
$$

## Question 2
Let two independent vectors $\mathbf a$  and $\mathbf b$. The scalar projection of vector $\mathbf a$ onto vector $\mathbf b$ is given by:

$$\text{Scalar Projection} = \frac{\left\langle\mathbf a , \mathbf b\right\rangle}{\lVert \mathbf b \rVert_2}$$

Now, we know that the Cauchy-Schwarz inequality states that:

$$
\begin{align*}
\left\langle \mathbf a, \mathbf b\right\rangle &\leq \lVert\mathbf a\rVert_2 \  \lVert\mathbf b\rVert_2 \\ \\
\therefore \frac{\left\langle \mathbf a, \mathbf b\right\rangle}{\lVert\mathbf b\rVert_2 } &\leq \lVert\mathbf a\rVert_2 \ 
\end{align*}
$$

Hence, proved.

## Question 3
Given $\mathbf{a} \in  \mathbb R^{+}$ and $\lVert\mathbf{a}\rVert_1 = 1$. Let  $\mathbf{a} = [a_1 \ a_2 \ \cdots \ a_N]^T$ such that

$$ \sum_{i=1}^n a_i = 1$$

Let us define a new vector $\mathbf{x}$ = $\mathbf{1}$ where $\mathbf{1}$ is a vector with all its elements equal to $1$.

Using Cauchy-Schwarz Inequality for $\mathbf{a}$ and $\mathbf{x}$,

$$ 
\begin{align*}
\left\lvert\langle \mathbf{a}, \mathbf{x}\right\rangle\rvert &\le \lVert\mathbf{a}\rVert_{2} \lVert\mathbf{x}\rVert_{2} \\
\implies  \left\lvert\langle \mathbf{a}, \mathbf{x}\right\rangle\rvert &\le  \lVert\mathbf{a}\rVert_{2} \sqrt{n}\\
\implies \sum_{i=1}^{n}a_ix_i &\le \lVert\mathbf{a}\rVert_{2} \sqrt{n} \\
\implies \sum_{i=1}^{n}a_i &\le \lVert\mathbf{a}\rVert_{2} \sqrt{n} \\
\implies {1 \over \sqrt{n}} &\le \lVert\mathbf{a}\rVert_{2} \\
\end{align*}
$$

Therefore, the minimum value of $||\mathbf{a}||_{2}$ is $\displaystyle {1 \over \sqrt{n}}$

## Question 4

$a)$ Considering the function $f : \mathbb R \to \mathbb{R}$ as follows

$$
\begin{align*}
f(\alpha_1) &= \lVert\mathbf{a} + \alpha_1 \mathbf{b}\rVert_2^2 \\
&= \left\langle \mathbf{a} + \alpha_1 \mathbf{b} , \mathbf{a} + \alpha_1 \mathbf{b}\right\rangle\\
&= \lVert\mathbf{a}\rVert_2^2 + 2\alpha_1 \left\langle\mathbf{a}, \mathbf{b}\right\rangle + \alpha_1^2 \lVert\mathbf{b}\rVert_2^2 \\
\end{align*}
$$

The given expression can be minimized by minimizing $f(\alpha_1)$

$$ 
\begin{align*}
\frac{\partial f(\alpha_1)}{\partial \alpha_1} &= 2 \left\langle\mathbf{a}, \mathbf{b}\right\rangle + 2 \alpha_1\lVert\mathbf{b}\rVert_2^2
\end{align*}
$$

$$ 
\begin{align*}
\frac{\partial^2 f(\alpha_1)}{\partial^2 \alpha_1} &= 2 \lVert\mathbf{b}\rVert_2^2 \ge 0
\end{align*}
$$ 

The given expression will have minima when $\displaystyle{\frac{\partial f(\alpha_1)}{\partial \alpha_1} = 0}$.

Therefore, for the required minima,

$$ 
\begin{align*}
\frac{\partial f(\alpha_1)}{\partial \alpha_1} &= 2 \left\langle \mathbf{a} , \mathbf{b}\right\rangle + 2 \alpha_1\|\mathbf{b}\|_2^2 = 0\\
\implies\alpha_1 &= - \frac{\left\langle \mathbf{a} , \mathbf{b}\right\rangle}{\lVert\mathbf{b}\rVert_2^2} \\
\end{align*}
$$ 

$b)$ Similarly considering the function $g : \mathbb R \to \mathbb{R}$ as follows

$$
\begin{align*}
g(\alpha_2) &= \lVert\mathbf{a} - \alpha_2 \mathbf{b}\rVert_2^2 \\
&= \left\langle \mathbf{a} - \alpha_2 \mathbf{b}, \mathbf{a} - \alpha_2 \mathbf{b}\right\rangle\\
&= \lVert\mathbf{a}\rVert_2^2 - 2\alpha_2 \left\langle \mathbf{a}, \mathbf{b}\right\rangle + \alpha_2^2 \lVert\mathbf{b}\rVert_2^2 \\
\end{align*}
$$

The given expression can be minimized by minimizing $g(\alpha_1)$

$$ 
\begin{align*}
\frac{\partial g(\alpha_2)}{\partial \alpha_2} &= - 2 \left\langle \mathbf{a}, \mathbf{b}\right\rangle + 2 \alpha_2\lVert\mathbf{b}\rVert_2^2
\end{align*}
$$

$$ \begin{align*}
\frac{\partial^2 g(\alpha_2)}{\partial^2 \alpha_2} &= 2 \lVert\mathbf{b}\rVert_2^2 \ge 0
\end{align*}
$$ 

The given expression will have maxima when $\displaystyle\frac{\partial g(\alpha_2)}{\partial \alpha_2} = 0 $.

Therefore for the required minima,

$$ 
\begin{align*}
\frac{\partial g(\alpha_2)}{\partial \alpha_2} &= - 2 \left\langle \mathbf{a}, \mathbf{b}\right\rangle + 2 \alpha_2\lVert\mathbf{b}\rVert_2^2 = 0\\
\implies\alpha_2 &=  \frac{\left\langle\mathbf{a}, \mathbf{b}\right\rangle}{\lVert\mathbf{b}\rVert_2^2} \\
\end{align*}
$$

## Question 5
Given $\mathbf{x}\in \mathbb{R}^N$. Let $\mathbf{x} = [x_1 \ x_2 \ x_3 \ \cdots x_N]^T$. The $L_P$ norm of a vector $\mathbf{x}$: 

$$
\lVert \mathbf{x} \rVert_P = \left(\sum_{i=1}^{N} |x_i|^P\right)^{1\over P}
$$

Consider $\lVert\mathbf{x}\rVert_1^2$ i.e., $\lVert\mathbf{x}\rVert_1^2 = \lVert\mathbf{x}\rVert_1\lVert\mathbf{x}\rVert_1$

$$
\begin{align*}
\lVert\mathbf{x}\rVert_1^2 &= \left(\sum_{i = 1}^{N} |x_i|\right)\left(\sum_{j = 1}^{N} |x_j|\right)\\\
\implies \lVert\mathbf{x}\rVert_1^2 &= \sum_{i=1}^N |x_i|^2 + \sum_{\substack{i,j\newline i\neq j}} |x_i||x_j|
\end{align*}
$$ 

Analyse the first summation of the RHS with respect to the $L_2$ norm i.e.,  $\displaystyle{\lVert\mathbf{x}\rVert_2^2  =  \sum_{i = 1}^{N} |x_i|^2}$

The first summation is simply the $L_2$ norm of $\mathbf{x}$ 

$$\implies  \lVert\mathbf{x}\rVert_1^2 = \lVert\mathbf{x}\rVert_2^2 + \sum_{\substack{i,j\newline i\neq j}} |x_i||x_j|$$

Now analyse the second summation. It is a summation of positive definites(absolute values). Hence, the summation is positive definite i.e.,

$$\sum_{\substack{i,j\newline i\neq j}} |x_i||x_j| \geq 0$$

$$
\implies \lVert\mathbf{x}\rVert_1^2 \geq \lVert\mathbf{x}\rVert_2^2\qquad 
$$

Note that one of the criteria to be classified as a norm is the positive definite property i.e., 

$$
\left(\sum_{i = 1}^{N} |x_i|^P\right)^{1\over P} \geq 0
$$

$$
\implies \lVert\mathbf{x}\rVert_1 \geq \lVert\mathbf{x}\rVert_2 \qquad\quad
$$
