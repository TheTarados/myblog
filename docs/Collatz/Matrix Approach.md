The Collatz conjecture is a well-known problem. I won't make the claim to make any new findings here. However, I have never seen the problem be approached like this (but well, I didn't search very much). So this could be of interest to you.

Let the Collatz process be defined as

$$
\left\{
	\begin{array}{ll}
	  \frac{3x_n+1}{2}=x_n+1\text{ if }x_n\text{ is odd}\\
	  \frac{x_n}{2}=x_n+1\text{ if }x_n\text{ is even}\\
	\end{array}
\right.
$$

Let

$$
\displaylines{
u_n = \left\{
	\begin{array}{ll}
	  3\text{ if }x_n\text{ is odd}\\
	  1\text{ if }x_n\text{ is even}\\
	\end{array}
\right.\\

v_n = \left\{
	\begin{array}{ll}
	  1\text{ if }x_n\text{ is odd}\\
	  0\text{ if }x_n\text{ is even}\\
	\end{array}
\right.
}
$$

we then have

$$
2x_{n+1}-u_nx_n=v_n.
$$

This is a linear equation. We can then define the two vectors

$$
\displaylines{
X = \begin{pmatrix}
	x_{0} \\
	x_{1} \\
	\vdots \\
	x_{n}
\end{pmatrix}\\
V = \begin{pmatrix}
	v_{0} \\
	v_{1} \\
	\vdots \\
	v_{n}
\end{pmatrix}
}
$$

Let also define the matrix

$$
U = \begin{pmatrix}
	-u_0& 2 & 0&0 & \cdots &0  \\
	0& -u_1 & 2& 0&\cdots&0 \\
	0&0&-u_2&2&\cdots&0\\
	0&0&0&-u_3&\cdots&0\\
	\vdots &\vdots& \vdots& \vdots& \ddots& \vdots \\
	2 & 0 &0  &0&\cdots&-u_n
\end{pmatrix}\\
$$

Note that all elements of the vectors should be positive integers to represent a valid Collatz sequence. 
We have a cycle in the Collatz sequence if

$$
UX=V
$$
To solve this, we can transform U in the following way:

| Transformation                        | $l_n$                                                                           |
| ------------------------------------- | ------------------ |
| $l_n\leftarrow u_0l_n+2l_0$           | $l_n = \begin{pmatrix} 0 &	4&0&0&\cdots&-u_0u_n\end{pmatrix}$                   |
| $l_n\leftarrow u_1l_n+4l_1$           | $l_n = \begin{pmatrix} 0 &	0&8&0&\cdots&-u_0u_1u_n\end{pmatrix}$                |
| $\vdots$                              | $\vdots$                                                                        |
| $l_n\leftarrow u_{n-1}l_n+2^nl_{n-1}$ | $l_n = \begin{pmatrix} 0 &	0&0&0&\cdots&2^{n+1}-\prod_{i=0}^n u_i\end{pmatrix}$ |

To keep equality, we apply the same transformation to $V$

| Transformation                        | $v_n$                                                                           |
| ------------------------------------- | ------------------ |
| $v_n\leftarrow u_0v_n+2v_0$           | $v_n = u_0v_n+2v_0$                   |
| $v_n\leftarrow u_1v_n+4v_1$           | $v_n = u_1(u_0v_n+2v_0)+4v_1$                |
| $\vdots$                              | $\vdots$                                                                        |
| $v_n\leftarrow u_{n-1}v_n+2^nv_{n-1}$ | $v_n = v_0\prod_{i=0}^{n-1}u_i+\sum_{i=0}^{n-1}(2^{i+1}v_i\prod_{j=i+1}^{n-1}u_j)$ |

The equality thus gives
$$
\left(2^{n+1}-\prod_{i=0}^nu_i\right)\underbrace{x_n}_{>0}=\underbrace{v_n\prod_{i=0}^{n-1}u_i}_{>0}+\underbrace{\sum_{i=0}^{n-1}\left(2^{i+1}v_i\prod_{j=i+1}^{n-1}u_j\right)}_{>0}
$$
For a valid cycle, we thus have
$$
2^{n+1}>\prod_{i=0}^{n}u_i=3^k
$$
with $k$, the number of odd numbers in the cycle.
This gives us an upperbound on the number of odd numbers in a cycle:
$$
\frac{n+1}{\log_2(3)}>k.
$$
I want to point out this is in now way new but I didn't see this way to get it, even if equivalent methods have probably been used.

If one could prove that
$$
\frac{v_n\prod_{i=0}^{n-1}u_i+\sum_{i=0}^{n-1}2^{i+1}v_i\prod_{j=i+1}^{n-1}u_i}{2^{n+1}-3^k}
$$
is never an positive integer other than 1 and 2, he would have proven that there is no other cycles. It would still not be sufficient to prove the Collatz conjecture as this does not eliminates the possibility that a sequence infinitely increases.