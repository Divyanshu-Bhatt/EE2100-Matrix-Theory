Matrix Theory: Assignment 3 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 3. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.

## Question 1

Given  $\set{\mathbf a, \mathbf b,\mathbf c}$ denotes a set of linearly independent vectors and $\set{\mathbf b_1, \mathbf b_2,\mathbf b_3}$ denotes the orthogonal basis obtained by applying the Grahm-Schmidt algorithm on $\set{\mathbf a, \mathbf b,\mathbf c}$.

$$
\begin{align*}
\implies&\mathbf b_1 = \mathbf a , \\ 
&\mathbf b_2 = \mathbf b - \mathbf {Proj_{\mathbf b_1}\mathbf b}, \\
&\mathbf b_3 = \mathbf c -\mathbf {Proj_{b_1}\mathbf c - Proj_{b_2}c }
\end{align*}
$$

$a)$ $\mathbf {b_3 \perp b_1 \Longleftrightarrow\displaystyle \mathbf{\langle b_1, b_3 \rangle } = 0}$ 

First, we will prove that $\mathbf {b_1 \perp b_2 \Longleftrightarrow
\displaystyle \mathbf{\langle b_1, b_2 \rangle } = 0}$

$$
\begin{align*}
\mathbf{\displaystyle \mathbf{\langle b_1, b_2 \rangle }} &= \mathbf{\langle a,\mathbf b -\mathbf  Proj_{b_1}\mathbf b \rangle} \\
&= \mathbf{\langle a, b \rangle} \mathbf{ - \langle a, \langle e_{b_1},b \rangle e_{b_1} \rangle}\\
&= \mathbf{\langle a, b \rangle} - \mathbf{\langle a, b \rangle} = 0
\end{align*}
$$

Therefore, $\mathbf {b_2 \perp b_1}.$ Now,

$$
\begin{align*}
\mathbf{\displaystyle \mathbf{\langle b_1, b_3 \rangle }} &= \mathbf{\langle a,\mathbf c -\mathbf { Proj_{b_1}\mathbf c - Proj_{b_2}c }\rangle}\\
&= \mathbf{\langle a,c \rangle - \langle a, \langle e_{b_1},c \rangle e_{b_1} \rangle - \langle a, \langle c, e_{b_2} \rangle e_{b_2} \rangle} \\
&= \mathbf{\langle a,c \rangle - \langle e_{b_1},c \rangle \langle a,  e_{b_1} \rangle - \langle c, e_{b_2} \rangle \langle a, e_{b_2} \rangle}  \tag {$ \mathbf{\langle a, e_{b_2} \rangle  = \lVert b \rVert _2 \langle b_1, b_2 \rangle = 0}$}\\
&= \mathbf{\langle a,c \rangle - \lVert a \rVert \langle e_a,c\rangle } - 0 \\
&= \mathbf{\langle a,c \rangle - \langle a,c\rangle } = 0
\end{align*}
$$

Thus, we have shown that $\mathbf {b_3 \perp b_1}.$ Now $\mathbf {b_2 \perp b_3 \Longleftrightarrow \displaystyle \mathbf{\langle b_2, b_3 \rangle } = 0}$

$$
\begin{align*}
\mathbf{\displaystyle \mathbf{\langle b_2, b_3 \rangle }} &= 
\mathbf{\langle b_2, \mathbf c -\mathbf { Proj_{b_1}\mathbf c - Proj_{b_2}c }\rangle }\\
&= \mathbf {\langle b_2,\mathbf c -\mathbf {Proj_{b_2}\mathbf c} \rangle - \mathbf {\langle b_2,\mathbf {Proj_{b_1}c}\rangle }} \\
&= (\mathbf{\langle b_2, c \rangle} \mathbf{ - \langle b_2, \langle e_{b_2},c \rangle e_{b_2} \rangle}) - \mathbf {\langle b_2,\mathbf {Proj_{b_1}c}\rangle }\\
&= 0 - \mathbf {\langle b_2, Proj_{b_1}c\rangle } \\
&= -\mathbf{\langle b - \langle e_{b_1},b \rangle e_{b_1}, (\mathbf {\langle c,e_{b_1} \rangle})e_{b_1}\rangle } \\
&= - \mathbf{ (\langle c,e_{b_1} \rangle) (\langle b, e_{b_1} \rangle - \langle b, e_{b_1}\rangle) } = 0 \\
\end{align*}
$$

Thus, we have shown that $\mathbf {b_2 \perp b_3}.$

$b)$ Given $\mathbb{W} = \mathbf{Span} \mathbf{\set{b_2, b_3}}.$

$$
\begin{align*}
\implies \mathbf{Proj}_{\mathbb{W}}\mathbf{b_1} &= \mathbf{Proj} _{\mathbf{b}_2}\mathbf{b}_1 + \mathbf{Proj} _{\mathbf{b}_3}\mathbf{b}_1\\
&= \frac{\mathbf {\langle b_1, b_2 \rangle}} { \lVert \mathbf b_2 \rVert _2}\mathbf e _{\mathbf b_2} + \frac{\mathbf {\langle b_1, b_3 \rangle}} { \lVert \mathbf b_3 \rVert _2} \mathbf e _{\mathbf b_3}  = 0
\end{align*}
$$

Therefore, $\mathbf{Proj}_{\mathbb{W}}\mathbf{b_1} = 0$.

## Question 2

Given finite length continuous time signals:

$$
s_1(t)=
    \begin{cases}
        0 & \text{if } t \le 0\\
        1 & \text{if }\ 0 \le t \le 2\\
        0 & \text{if } t \ge 2\\
    \end{cases}
$$

$$
s_2(t)=
    \begin{cases}
        0 & \text{if } t \le 0\\
        1 & \text{if } 0 \le t \le 1\\
        -1 & \text{if } 1 \le t \le 2\\
        0 & \text{if } t \ge 2
    \end{cases}
$$

$$
s_3(t)=
    \begin{cases}
        0 & \text{if } t \le 0\\
        1 & \text{if } 0 \le t \le 2\\
        -1 & \text{if } 2 \le t \le 3\\
        0 & \text{if } t \ge 3
    \end{cases}
$$

$$
s_4(t)=
    \begin{cases}
        0 & \text{if } t \le 0\\
        -1 & \text{if } 0 \le t \le 3\\
        0 & \text{if } t \ge 3
    \end{cases}
$$

$a)$ The orthogonal basis of the subspace spanned by the vectors $s_1(t)$, $s_2(t)$, $s_3(t)$ and $s_4(t)$ can be found using Grahm Schmidt Algorithm.

$$
\langle s_1(t), s_1(t) \rangle = \displaystyle{\int_{-\infty}^\infty s_1(t)s_1^*(t)dt}
$$

but $s_1(t)$, $s_2(t)$, $s_3(t)$ and $s_4(t)$ are real

$$
\implies \langle s_1(t), s_1(t) \rangle = \displaystyle{\int_{-\infty}^\infty (s_1(t))^2dt} 
$$

Let the basis be $\phi_1(t)$, $\phi_2(t)$, $\phi_3(t)$ and $\phi_4(t)$.

$$ 
\begin{align*}
\phi_1(t) &= \frac{s_1(t)}{\lVert s_1(t) \rVert_2} \\
{\lVert s_1(t) \rVert_2^2} &= \langle s_1(t), s_1(t) \rangle \\
&= \displaystyle{\int_{-\infty}^\infty (s_1(t))^2 dt} \\ 
&= \displaystyle{\int_{0}^2 1 dt } = 2 
\end{align*}
$$

$$
\implies \phi_1(t) = {\phi_1'(t) \over\lVert \phi_1'(t) \rVert} = \displaystyle{{s_1(t)\over \sqrt2}} =
    \begin{cases}
        0 &  t \le 0\\
        1\over \sqrt2 & \ 0 \le t \le 2\\
        0 &  t \ge 2\\
    \end{cases}
$$

Calculating $\phi_2(t)$. Defining $\phi_2'(t)$ as follows

$$
\phi_2'(t) = s_2(t) - \langle s_2(t), \phi_1(t) \rangle \phi_1(t)\\
$$

then, $\phi_2(t) = \displaystyle{\frac{\phi_2'(t)}{\lVert \phi_2'(t) \rVert}_2}$  

$$
\begin{align*}
\phi_2'(t) &= s_2(t) - \left(\int_{-\infty}^\infty s_2(t)\phi_1(t)dt\right)\phi_1(t)\\
&=s_2(t)-\left(\int_{-\infty}^\infty {1\over\sqrt2}s_1(t)s_2(t)dt\right)\phi_1(t) \\
&=s_2(t)-\left(\int_{0}^2 {1\over\sqrt2}s_2(t)dt\right)\phi_1(t) \\ 
&=s_2(t)-{\phi_1(t)\over \sqrt2}\left(\int_{0}^1 1dt + \int_{1}^2 -1dt\right) \\ 
&=s_2(t)\\
\end{align*}
$$

$$
\begin{align*}
{\lVert \mathbf {\phi_2'}(t) \rVert_2^2} &= \langle s_2(t), s_2(t) \rangle \\
&= \displaystyle{\int_{-\infty}^\infty (s_2(t))^2 dt} \\
&= \displaystyle{\int_{0}^2 1 dt} = 2\\
\end{align*}
$$

$$
\implies\phi_2(t)= {\phi_2'(t)\over \lVert \phi_2'(t)\rVert}_2 = 
    \begin{cases}
        0 & t \le 0\\
        1\over \sqrt{2} &  0 \le t \le 1\\
        -1\over{\sqrt2} &  1 \le t \le 2\\
        0 &  t \ge 2
    \end{cases}
$$

Calculating $\phi_3(t)$. Defining $\phi_3'(t)$ as follows

$$
\begin{align*}
\phi_3'(t) &= s_3(t) - \langle s_3(t), \phi_1(t) \rangle \phi_1(t) - \langle s_3(t), \phi_2(t) \rangle \phi_2(t)\\
&= s_3(t)-\left(\displaystyle{\int_{-\infty}^\infty s_3(t)\phi_1(t)}dt\right)\phi_1(t) -\left(\displaystyle{\int_{-\infty}^\infty s_3(t)\phi_2(t)}dt\right)\phi_2(t) \\
&= s_3(t)-\left(\displaystyle{\int_{0}^2 s_3(t)}dt\right){\phi_1(t)\over \sqrt2} -\left(\displaystyle{\int_{0}^1 s_3(t)}dt - \int_{1}^2 s_3(t)dt\right){\phi_2(t)\over \sqrt2} \\
&= s_3(t)-\left(\displaystyle{\int_{0}^2 1}dt\right){\phi_1(t)\over \sqrt2} -\left(\displaystyle{\int_{0}^1 1}dt - \int_{1}^2 1dt\right){\phi_2(t)\over \sqrt2} \\
&= s_3(t) - \sqrt2 \phi_1(t)\\
&= s_3(t) - s_1(t)\\
\end{align*}
$$

$$
\phi_3'(t) =
    \begin{cases}
        0 &  t \le 2\\
        -1 &  2 \le t \le 3\\
        0 &  t \ge 3
    \end{cases}\\
$$

$$
\begin{align*}
{\lVert \mathbf {\phi_3'} (t)\rVert_2^2} &= \displaystyle{\int_{-\infty}^\infty (\phi_3'(t))^2 dt}  \\
&= \displaystyle{\int_{2}^3 1 dt} = {1}\\
\end{align*}
$$

$$
\implies \phi_3(t) = {\phi_3'(t) \over \lVert \phi_3'(t) \rVert}_2  = \begin{cases}
        0 &  t \le 2\\
        -1 &  2 \le t \le 3\\
        0 &  t \ge 3
    \end{cases}
$$

Calculating $\phi_4(t)$. Defining $\phi_4'(t)$ as follows

$$
\begin{align*}
\phi_4'(t) &= s_4(t) - \langle s_4(t), \phi_1(t) \rangle \phi_1(t) - \langle s_4(t), \phi_2(t) \rangle \phi_2(t) - \langle s_4(t), \phi_3(t) \rangle \phi_3(t)\\
 &= s_4(t) - \left(\displaystyle{\int_{-\infty}^\infty s_4(t)\phi_1(t)dt}\right)\phi_1(t) - \left(\displaystyle{\int_{-\infty}^\infty } s_4(t)\phi_2(t)dt\right)\phi_2(t) - \left(\int_{-\infty}^\infty s_4(t)\phi_3(t)\right)\phi_3(t)\\ 
&= s_4(t) - \left(\int_{0}^2 s_4(t)dt\right){\phi_1(t)\over \sqrt2} - \left({\int_{0}^1 s_4(t)dt} - {\int_{1}^2 s_4(t)dt}\right){\phi_2(t)\over \sqrt2} - \left({\int_{2}^3 {-}{s_4(t) }dt}\right)\phi_3(t)\\ 
&= s_4(t) -\left(\int_0^2 {-1} dt\right){\phi_1(t)\over \sqrt2} - \left(\int_0^1-1dt + \int_1^21dt\right){\phi_2(t)\over \sqrt2} - \left(\int_2^3 1dt\right){\phi_3(t)}\\
&= s_4(t)  + \sqrt2\phi_1(t) - \phi_3(t)\\
&= s_4(t)  + s_1(t) - s_3(t) + s_1(t)\\
&= s_4(t)  + 2s_1(t) - s_3(t)\\
\end{align*}
$$

$$
\phi_4'(t)= 0
$$

$$
\implies \phi_4(t)= 0
$$

$\implies \phi_4(t)$ doesnt exist, i.e, the signals $\phi_1(t)$, $\phi_2(t)$ and $\phi_3(t)$ are the orthogonal(orthonormal to be specific) basis of the signal space spanned by $s_1(t), s_2(t), s_3(t)$ and $s_4(t)$.  


$b)$ A brute force method to check whether the ordering of signals changes the basis would be to perform the Grahm Schmidt algorithm on the new ordering and check if the basis is the same as the previous one. Let the orthogonal basis of the signal space spanned by the signals $s_2(t)$, $s_3(t)$, $s_1(t)$ and $s_4(t)$ be $\phi_1(t)$, $\phi_2(t)$, $\phi_3(t)$ and $\phi_4(t)$.

$$ 
\begin{align*}
\phi_1(t) &= { s_2(t)\over \lVert s_2(t) \rVert_2} \\
{\lVert s_2(t) \rVert_2^2} &= \langle s_2(t), s_2(t) \rangle\\ 
&= \displaystyle{\int_{-\infty}^\infty (s_2(t))^2 dt}\\ 
&= \displaystyle{\int_{0}^1 1 dt+ \int_{1}^2 1 dt} = 2\\
\implies \phi_1(t) &= {s_2(t)\over \sqrt{2}}
\end{align*}
$$

$$
\phi_1(t)=
    \begin{cases}
        0 &  t \le 0\\
        1\over \sqrt2 &  0 \le t \le 1\\
        -1\over \sqrt2 &  1 \le t \le 2\\
        0 & t \ge 2
    \end{cases}
$$

Calculating $\phi_2(t)$. Defining $\phi_2'(t)$ as follows

$$
\begin{align*}
\phi_2'(t) &= s_3(t) - \langle s_3(t), \phi_1(t) \rangle \phi_1(t)\\
&= s_3(t) - \left(\displaystyle{\int_{-\infty}^\infty s_3(t)\phi_1(t)dt}\right)\phi_1(t)\\
&= s_3(t) - \left(\int_{0}^1 s_3(t)dt - \int_{1}^2 s_3(t)dt\right){\phi_1(t)\over\sqrt2}\\
&= s_3(t) - \left(\int_{0}^1 {1}dt  - \int_{1}^2 {1}dt\right){\phi_1(t)\over \sqrt2} \\
&= s_3(t)
\end{align*}
$$

$$
\begin{align*}
{\lVert \mathbf {\phi_2'}(t) \rVert_2^2} &= \langle s_3(t), s_3(t) \rangle \\
&= \displaystyle{\int_{-\infty}^\infty (s_3(t))^2 dt} \\
&= \displaystyle{{\int_{0}^2 1 dt} + \int_{2}^3 1 dt} = 3\\
\end{align*}
$$

$$
\begin{align*}
\implies \phi_2(t) = {\phi_2'(t) \over \lVert \phi_2'(t) \rVert _2} = {s_3(t)\over \sqrt3}
\end{align*}
$$

$$
\phi_2(t)=
    \begin{cases}
        0 & \text{if } t \le 0\\
        1\over \sqrt3 & \text{if } 0 \le t \le 2\\
        -1\over \sqrt3 & \text{if } 2 \le t \le 3\\
        0 & \text{if } t \ge 3
    \end{cases}
$$

Calculating $\phi_3(t)$. Defining $\phi_3'(t)$ as follows

$$
\begin{align*}
\phi_3'(t) &= s_1(t) - \langle s_1(t), \phi_1(t) \rangle \phi_1(t) - \langle s_1(t), \phi_2(t) \rangle \phi_2(t)\\
&= s_1(t)-\left(\displaystyle{\int_{-\infty}^\infty s_1(t)\phi_1(t)}dt\right)\phi_1(t) -\left(\displaystyle{\int_{-\infty}^\infty s_1(t)\phi_2(t)}dt\right)\phi_2(t) \\
&= s_1(t)-\left(\displaystyle{\int_{0}^1 s_1(t)}dt - \int_{1}^2 s_1(t)dt\right){\phi_1(t)\over \sqrt2} -\left(\displaystyle{\int_{0}^2 s_1(t)}dt - \int_{2}^3 s_1(t)dt\right){\phi_2(t)\over \sqrt3} \\
&= s_1(t)-\left(\displaystyle{\int_{0}^1 1}dt - \int_{1}^2 1dt\right){\phi_1(t)\over \sqrt2} -\left(\displaystyle{\int_{0}^2 1}dt - \int_{2}^3 0dt\right){\phi_2(t)\over \sqrt3} \\
&= s_1(t) - {2\over\sqrt3} \phi_2(t)\\
&= s_1(t) - {2s_3(t)\over 3}\\
\end{align*}
$$

$$
\phi_3'(t) =
    \begin{cases}
        0 &  t \le 0\\
        1\over 3 &  0 \le t \le 2\\
        2\over 3 &  2 \le t \le 3\\
        0 &  t \ge 3
    \end{cases}\\
$$

$$
\begin{align*}
{\lVert \mathbf {\phi_3'} (t)\rVert_2^2} &= \displaystyle{\int_{-\infty}^\infty (\phi_3'(t))^2 dt}  \\
&= \displaystyle{\int_{0}^2 {1\over 9} dt + \int_{2}^3 {4\over9} dt} = {{2\over 3}}\\
\end{align*}
$$

$$
\implies \phi_3(t) = {\phi_3'(t) \over \lVert \phi_3'(t) \rVert}_2  = 
    \begin{cases}
        0 &  t \le 0\\
        1\over \sqrt6 &  0 \le t \le 2\\
        \sqrt{2\over 3} &  2 \le t \le 3\\
        0 &  t \ge 3
    \end{cases}\\
$$

Calculating $\phi_4(t)$. Defining $\phi_4'(t)$ as follows

$$
\begin{align*}
\phi_4'(t) &= s_4(t) - \langle s_4(t), \phi_1(t) \rangle \phi_1(t) - \langle s_4(t), \phi_2(t) \rangle \phi_2(t) - \langle s_4(t), \phi_3(t) \rangle \phi_3(t)\\
 &= s_4(t) - \left(\displaystyle{\int_{-\infty}^\infty s_4(t)\phi_1(t)dt}\right)\phi_1(t) - \left(\displaystyle{\int_{-\infty}^\infty } s_4(t)\phi_2(t)dt\right)\phi_2(t) - \left(\int_{-\infty}^\infty s_4(t)\phi_3(t)\right)\phi_3(t)\\ 
&= s_4(t) - \left(\int_{0}^1 s_4(t)dt - \int_{1}^2 s_4(t)dt \right){\phi_1(t)\over \sqrt2} - \left({\int_{0}^2 s_4(t)dt} - {\int_{2}^3 s_4(t)dt}\right){\phi_2(t)\over \sqrt3} - \left({\int_{0}^2 {s_4(t) }dt} + \int_{2}^3 {2s_4(t) }dt\right){\phi_3(t)\over \sqrt6}\\ 
&= s_4(t) -\left(\int_0^1 {-1} dt + \int_1^2 {1} dt\right){\phi_1(t)\over \sqrt2} - \left(\int_0^2 -1dt + \int_2^3 1dt\right){\phi_2(t)\over \sqrt3} - \left(\int_0^2 -1dt + \int_2^3 -2dt\right){\phi_3(t)\over \sqrt6}\\
&= s_4(t)  + {\phi_2(t)\over \sqrt3} + {2\sqrt2\phi_3(t)\over \sqrt3}\\
&= s_4(t)  + {s_3(t)\over 3} + 2s_1(t) - {4s_3(t)\over3}\\
&= s_4(t)  + 2s_1(t) - s_3(t)\\
\end{align*}
$$

$$
\phi_4'(t)= 0
$$
$$
\implies \phi_4(t)= 0
$$


Note that these signals obtained are different from the ones obtained in part $(a)$. Hence, the ordering of the signals does affect the basis. This also goes to show that the computational effort varies based upon the order in which the signals are taken.


## Question3

$a)$ The discrete time signals given can be represented in a vectorial format as follows:

$$
\begin{align*}
\mathbf{x_1}&= \begin{bmatrix} 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 \end{bmatrix}^T\\ 
\mathbf{x_2}&= \begin{bmatrix} 1 & 1 & 1 & 1 & -1 & -1 & -1 & -1 \end{bmatrix}^T\\ 
\mathbf{x_3}&= \begin{bmatrix} 0 & 0.25 & 0.5 & 1 & 1 & 0.5 & 0.25 & 0 \end{bmatrix}^T\\ 
\mathbf{x_4}&= \begin{bmatrix} -1 & -1 & -1 & -1 & 1 & 1 & 1 & 1 \end{bmatrix}^T
\end{align*}
$$

$b)$ Let the orthogonal basis be $\mathbf{B}=\set{\mathbf{u_1},\mathbf{u_2},\mathbf{u_3},\mathbf{u_4}}$. In accordance with the Grahm Schmidt Algortihm, the basis generated would be as follows: (Note how normalization helps with projection calculations)

$$
\mathbf{u_1}={\mathbf{x_1} \over \lVert \mathbf{x_1}  \rVert} \\
~\\
\mathbf{u_2}={\mathbf{x_2}-\langle\mathbf{x_2},\mathbf{u_1}\rangle \over \lVert  \mathbf{x_2} \langle\mathbf{x_2},\mathbf{u_1}\rangle \rVert} \\
~\\
\mathbf{u_3}={\mathbf{x_3}-\langle\mathbf{x_3},\mathbf{u_1}\rangle-\langle\mathbf{x_3},\mathbf{u_2}\rangle \over \lVert \mathbf{x_3}-\langle\mathbf{x_3},\mathbf{u_1}\rangle-\langle\mathbf{x_3},\mathbf{u_2}\rangle\rVert} \\
~\\
\mathbf{u_4}={\mathbf{x_4}-\langle\mathbf{x_4},\mathbf{u_1}\rangle-\langle\mathbf{x_4},\mathbf{u_2}\rangle - \langle\mathbf{x_4},\mathbf{u_3}\rangle\over \lVert \mathbf{x_3}-\langle\mathbf{x_4},\mathbf{u_1}\rangle -\langle\mathbf{x_4},\mathbf{u_2}\rangle - \langle\mathbf{x_4},\mathbf{u_3}\rangle  \rVert}
$$

Solving, we get the basis as: 

$$
\begin{align*}
\mathbf{u_1}&= \begin{bmatrix} {\sqrt{2} \over 4} &{\sqrt{2} \over 4} & {\sqrt{2} \over 4} &{\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {\sqrt{2} \over 4}  \end{bmatrix}^T\\
\mathbf{u_2}&= \begin{bmatrix} {\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {-\sqrt{2} \over 4} & {-\sqrt{2} \over 4} & {-\sqrt{2} \over 4} & {-\sqrt{2} \over 4}  \end{bmatrix}^T\\ 
\mathbf{u_3}&= \begin{bmatrix} {-\sqrt{70} \over 20}  &{-3\sqrt{70} \over 140}&  {\sqrt{70} \over 140}&  {9\sqrt{70} \over 140} & {9\sqrt{70} \over 140} & {\sqrt{70} \over 140} & {-3\sqrt{70} \over 140} & {-\sqrt{70} \over 20} \end{bmatrix}^T\\ 
\mathbf{u_4}&= \begin{bmatrix} 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0  \end{bmatrix}^T 
\end{align*}
$$ 

Thus, $\mathbf{u_4}$ isn't a basis vector, since it is redundant. $\mathbf{B}=\set{\mathbf{u_1},\mathbf{u_2},\mathbf{u_3}}$ 

$c)$ The signal representation of the basis vectors calculated above is:

<p align="center">
     <img src="https://github.com/Divyanshu-Bhatt/MT/blob/main/images/signal1.svg" width="300"/>
</p>

<p align="center">
     <img src="https://github.com/Divyanshu-Bhatt/MT/blob/main/images/signal2.svg" width="300"/>
</p>

<p align="center">
     <img src="https://github.com/Divyanshu-Bhatt/MT/blob/main/images/signal3.svg" width="300"/>
</p>

$d)$ In general, we expect a different basis due to a different order. However, in this case, the basis obtained will be the same. The only difference is when we apply the algorithm in this order, we get $\mathbf{u_3}$ as the zero vector instead of $\mathbf{u_4}$ and $\mathbf{u_1}$, $\mathbf{u_2}$, are obatined in the opposite order. Thus, we have: 

$$ 
\begin{align*}
\mathbf{u_1}&= \begin{bmatrix} {\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {-\sqrt{2} \over 4} & {-\sqrt{2} \over 4} & {-\sqrt{2} \over 4} & {-\sqrt{2} \over 4}  \end{bmatrix}^T\\
\mathbf{u_2}&= \begin{bmatrix} {\sqrt{2} \over 4} & {\sqrt{2} \over 4} &{\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {\sqrt{2} \over 4} & {\sqrt{2} \over 4} &{\sqrt{2} \over 4} & {\sqrt{2} \over 4}  \end{bmatrix}^T\\
\mathbf{u_3}&= \begin{bmatrix} 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0  \end{bmatrix} ^T\\
\mathbf{u_4}&= \begin{bmatrix} {-\sqrt{70} \over 20} & {-3\sqrt{70} \over 140} & {\sqrt{70} \over 140} & {9\sqrt{70} \over 140} & {9\sqrt{70} \over 140} & {\sqrt{70} \over 140} & {-3\sqrt{70} \over 140} & {-\sqrt{70} \over 20}  \end{bmatrix}^T
\end{align*}
$$ 






