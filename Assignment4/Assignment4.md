Matrix Theory: Assignment 4 Solutions 
====================================

## General Instructions
The following document contains the solutions to the theory-based questions for Assignment 4. Please note that the solutions provided may not be the only possible way to solve the questions. They indicate only one of the many (possibly) valid solutions. The solutions provided are relatively crisp and do not include all the steps that you must have. Your solution should be logical and contain all supporting arguments. Feel free to contact us via email in case you find any discrepancy in the solutions provided.


## Question 2

$a)$ In an adjacency matrix, each entry is either $0$ or $1$, depending on whether an edge exists or not between two nodes(vertices). Hence, we can say that the field of the matrix is $\set{0, 1}$. It is a Binary Field.

$b)$ If there are no self-loops in the graph, all the diagonal terms in the adjacency matrix will be zero. Hence, the trace of the matrix will also be zero. This condition is violated in the presence of one or more self-loops.

$c)$ The primary difference between the adjacency matrix of a directed and an undirected graph is that the adjacency matrix of a undirected graph is always symmetric whereas this is not necesarily true for a directed graph. The reason being, in an undirected graph, the edge between the vertices is in both directions, which is reflected in the graph i.e. $A_{ij} = A_{ji}$. This is not true for a directed graph.

$d)$ The degree of a vertex of a graph refers to the number of edges incident to that vertex. Thus, in an adjacency matrix, we can find this value by calculating the sum of all the entries in a column or a row. Since the entries for non-connected vertices are $0$, the answer will be equal to the number of connected vertices. Mathematically, 

$$
\begin{align*}
\mathrm{deg}(v) &= \sum_{i=0}^{n}A_{vi} \\
&= \sum_{j=0}^{n}A_{jv}
\end{align*}
$$

where $n$ is the number of vertices and $a_{ij}$ denotes the value of the entry at the $i^{th}$ row and $j^{th}$ column of the adjacency matrix.

Alternatively, this can also be achieved by finding the dot product of a row or column vector with itself. 

$e)$ Given that there are no self loops, each value in $\mathbf A^2$ corresponds to $A_{ii}$ i.e. the diagonal values will be equal to the degree of the corresponding vertex. Hence, the summation of the diagonal values is equal to twice the total number of edges in the graph.

$$
\implies \text{trace}(\mathbf A^2) = 2m
$$

Please note that this is valid for simple graphs only.

$f)$ **Claim:** The number of walks of length $k$ between $v_i$ and $v_j$ is given by $\left(A^K\right)_{ij}$ i.e. the $ij^{th}$ entry of the matrix $\mathbf A^K$.

Proving the above claim by induction:

For $k = 1$, the number of walks between the $v_i$ and $v_j$ is given by $A_{ij}$ because $A_{ij}=1$ implies that there is an edge between the two vertices, which is a walk of length $1$, and $A_{ij}=0$ means that no such walk exists. 

Assuming the claim to be true for all $k \in \set{1,\cdots, k_0}$ 

We attempt to prove it for $k = k_0 + 1$. Any walk of length $k_0+1$ from $v_i$ to $v_j$ consists of a walk of length $k$ from $v_i$ to a neighbour of $v_j$. 

For $v_p \in N(v_j)$  i.e. $v_p$ is a neighbour of $v_j$, the number of walks of length $k$ between $v_i$ and $v_p$ is given by $\left(A^{k_0}\right)_{ip}$.

$$
\begin{align*}
W(v_i, v_j, k+1) &= \sum_{v_p \in N(j)}W(v_i, v_p, k) \\
&= \sum_{v_p\in N(j)} A^K_{ip}\\
&= \sum_{m=1}^{n}A_{im}^KA_{mj}\\
&= A^{K+1}_{ij}
\end{align*}
$$

where $W(v_i, v_j, k)$ denotes the number of walks of length $k$ between $v_i$ and $v_j$. The summation obtained is the $ij^{th}$ entry of the matrix obtained by multiplying $\mathbf A^K$ with $\mathbf A$. Hence, the claim is true for $k = k_0 + 1$.

### Note
The $ij^{th}$ entry of the matrix $\mathbf Z \in \mathbb{R}^{m\times p}$  obtained by multiplying the matrices $\mathbf X \in \mathbb{R}^{m\times n}$ and $\mathbf Y \in \mathbb{R}^{n\times p}$ is given by 

$$
Z_{ij} = \sum_{k=1}^{n}x_{ik}y_{kj}
$$

## Question 3

The adjacency matrix for a graph with $n$ nodes $\mathbf A$ $(\mathbf A \in \mathbb R^{n \times n})$ validates the existence of a connection between 2 points in a graph. For an undirected graph,

$$
\mathbf A_{ij} = \begin{cases}
      1 &  \text{if $\exists$ a link between $i$ and $j$}\\
      0 &  \text{otherwise} \\
\end{cases} 
$$

$$
\mathbf A = \begin{bmatrix}
0 & 1 & 1 & 0 & 0 & 0 \\
1 & 0 & 1 & 1 & 1 & 1 \\
1 & 1 & 0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 1 & 0 \\
0 & 1 & 0 & 1 & 0 & 1 \\
0 & 1 & 0 & 0 & 1 & 0 \\
\end{bmatrix}
$$

The incidence matrix for a graph with $m$ edges and $n$ nodes $\mathbf B$ $(\mathbf B \in \mathbb R^{ m \times n})$ checks for the incidence of vertex $j$ upon edge $i$ in a graph. For an undirected graph,

$$
\mathbf B_{ij} = \begin{cases}
      1 &  \text{if vertex $j$ lies on the edge $i$}\\
      0 &  \text{otherwise} \\
\end{cases} 
$$

$$
\mathbf B = \begin{bmatrix}
1 & 1 & 0 & 0 & 0 & 0 \\
1 & 0 & 1 & 0 & 0 & 0 \\
0 & 1 & 1 & 0 & 0 & 0 \\
0 & 1 & 0 & 1 & 0 & 0 \\
0 & 1 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 & 1 & 0 \\
0 & 1 & 0 & 0 & 0 & 1 \\
0 & 0 & 0 & 0 & 1 & 1 \\
\end{bmatrix}
$$

## Question 4
The output of a system ( say $y[n]$ ) is given by the convolution of the input with the impulse response of the system. We can write this as:

$$ 
y[n] = x[n] * h[n] 
$$

The linear convolution sum can be written as a matrix-vector product with help of the Toeplitz matrix.

The Toeplitz matrix of the impulse response is given by:

$$
\mathbf{H} = \begin{bmatrix} 1 & 0 & 0 & 0\\
 1 & 1 & 0 & 0  \\
 0 & 1 & 1 & 0  \\
 0 & 0 & 1 & 1 \\
 1 & 0 & 0 & 1  \\
 0 & 1 & 0 & 0 \\
 1 & 0 & 1 & 0  \\
 0 & 1 & 0 & 1 \\
 0 & 0 & 1 & 0 \\
 0 & 0 & 0 & 1  \\
 0 & 0 & 0 & 0 
\end{bmatrix}
$$

Now, we can write the convolution sum as:

$$
\begin{align*}
y[n] &= \mathbf{H}[n] \ x[n] \\
&= \begin{bmatrix} 1 & 0 & 0 & 0\\
 1 & 1 & 0 & 0  \\
 0 & 1 & 1 & 0  \\
 0 & 0 & 1 & 1 \\
 1 & 0 & 0 & 1  \\
 0 & 1 & 0 & 0 \\
 1 & 0 & 1 & 0  \\
 0 & 1 & 0 & 1 \\
 0 & 0 & 1 & 0 \\
 0 & 0 & 0 & 1  \\
 0 & 0 & 0 & 0 
\end{bmatrix}
\begin{bmatrix} 1 \\
2 \\
3 \\
4 \end{bmatrix} \\
&= \begin{bmatrix} 1 & 3 & 5 & 7 & 5 & 2 & 4 & 6 & 3 & 4 & 0\end{bmatrix}^{T}
\end{align*} $$

## Question 5
$a)$ Consider the given circuit.

<p align="center">
     <img src="https://github.com/Divyanshu-Bhatt/EE2100-Matrix-Theory/blob/main/Assignment4/images/circuit1.svg" width="300"/>
</p>

As the inductor has a reading of $2\Omega$, you can consider the impedance to be  $j2\Omega$. Else, considering the inductance as $2H$, the impedance is  $j\omega \times2$  = $j100\times2$ = $j200 \Omega$.
The other inductor has an inductance of 0.02H. Hence, the impedance  is  $j\omega \times0.02$  = $j100\times0.02$ = $j2 \Omega$.

This solution has been made assuming $j2\Omega$. 

Consider that the matrix-vector product is to be made wrt $V_A$ and $V_B$. This means that the resistance $10\Omega$ and impedance $j2\Omega$ can be considered to be in series. The effective impedance thus becomes $(10 + 2j)\Omega$

<p align="center">
     <img src="https://github.com/Divyanshu-Bhatt/EE2100-Matrix-Theory/blob/main/Assignment4/images/circuit2.svg" width="300"/>
</p>

From the circuit, 

$$
V_A - V_B = V_s = 10\sin(100t+{\pi\over4})
$$

If written directly as a matrix-vector product, we have 

$$
\begin{equation}\begin{bmatrix} 1 & -1\end{bmatrix} \begin{bmatrix} V_A \\\ V_B\end{bmatrix}= 10\sin(100t+{\pi\over4}) \end{equation}
$$ 

Perform nodal analysis at Node A:

$$
\begin{align*}
i_s &= {V_A-V_B\over j2} + {V_A-V_B\over 10+j2}\\
&= V_A\left({1\over j2} + {1\over 10+j2}\right)-V_B\left({1\over j2} + {1\over 10+j2}\right) \\ 
&= \begin{bmatrix} {1\over j2} + {1\over 10+j2} & -{1\over j2} - {1\over 10+j2}\end{bmatrix} \begin{bmatrix} V_A \\\ V_B\end{bmatrix}\\
\end{align*}
$$

Another possibility would be combining these equations into a common matrix-vector product.

$$
\implies \begin{bmatrix} i_s \\\ 0\end{bmatrix} = \begin{bmatrix} {1\over j2} + {1\over 10+j2} & -{1\over j2} - {1\over 10+j2} \\\ 1 & -1\end{bmatrix} \begin{bmatrix} V_A \\\ V_B\end{bmatrix}
$$

One solution can be made without considering $V_A$ and $V_B$ too. Consider the following circuit and notations.

<p align="center">
     <img src="https://github.com/Divyanshu-Bhatt/EE2100-Matrix-Theory/blob/main/Assignment4/images/circuit3.svg" width="300"/>
</p>

At Node 1,

$$
i_s = {V_1\over j2} + {{V_1-V_2}\over 10}  
$$

At Node 2,

$$
{V_2\over j2} + {{V_2-V_1}\over 10} = 0 
$$

Also, 

$$
V_1 = V_s
$$

Substituting the third equation in the second, 

$$
\begin{align*}
{V_2\over j2} + {{V_2-V_s}\over 10} &= 0\\
\implies V_2\left({1\over j2} - {1\over 10}\right) &= {V_s\over 10}\\
\implies \begin{bmatrix} {1\over j2} - {1\over 10}\end{bmatrix} \begin{bmatrix} V_2 \end{bmatrix} &= \begin{bmatrix} V_s\over 10 \end{bmatrix}
\end{align*}
$$


$b)$ Consider the given circuit.

<p align="center">
     <img src="https://github.com/Divyanshu-Bhatt/EE2100-Matrix-Theory/blob/main/Assignment4/images/circuit4.svg" width="300"/>
</p>

This solution too can be made using various methods. The one that has been followed here is using the notation below. Assume that $\omega$ of the current source = $100 s^{-1}$. 

<p align="center">
     <img src="https://github.com/Divyanshu-Bhatt/EE2100-Matrix-Theory/blob/main/Assignment4/images/circuit5.svg" width="300"/>
</p>

From the circuit, $V_5 = -2V$.

At Node 1,

$$
\begin{align*}
i_s &= {{V_1-V_2}\over 10} \\ 
&= {V_1\over 10}-{V_2\over 10}
\end{align*}
$$

At Node 2,

$$
\begin{align*}
{V_2\over j2} + {{V_2-V_1}\over 10} + {{V_2-V_3}\over -j2} &= 0\\ 
\implies {-V_1\over 10} + V_2\left({1\over j2} + {1\over 10} + {1\over -j2}\right) -{V_3\over -j2}  &= 0 
\end{align*}
$$

At Node 3,

$$
\begin{align*}
{V_3-V_4\over 5} + {{V_3-V_2}\over -j2} &= 0\\
\implies {V_2\over j2} + V_3\left({1\over 5} + {1\over -j2}\right) - {V_4\over5} &= 0
\end{align*}
$$

At Node 4,

$$
\begin{align*}
{V_4-V_3\over 5} + {{V_4-V_5}\over j1} &= 0\\ 
\implies {-V_3\over 5} + V_4\left({1\over 5} + {1\over j1}\right) &= {-2\over j1} 
\end{align*}
$$

These four final euqations can be written as a matrix-vector product. i.e.,

$$
\begin{bmatrix}1\over 10 & -1\over 10 & 0 & 0 \\\ -1\over 10 & {1\over j2} + {1\over 10} + {1\over -j2} & 1\over -j2 & 0\\\ 0 & 1\over j2 & {1\over 5} + {1\over -j2} & 1\over 5\\\ 0 & 0 & -1\over 5 & {1\over 5} + {1\over j1}\end{bmatrix}
\begin{bmatrix} V_1\\\ V_2\\\ V_3\\\ V_4 \end{bmatrix} 
= \begin{bmatrix} i_s\\\ 0 \\\ 0 \\\ -2\over j1 \end{bmatrix}
$$

### Note
As there are multiple correct approaches to each part of this question, marks will be awarded regardless of the method chosen if a correct matrix vector product is formed.
