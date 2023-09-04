[It is known](https://en.wikipedia.org/wiki/Iterated_function#Examples) that the superfunction of any rational linear function can be found. As I computed it by myself before finding it elsewhere, I will showcase my method here. It does not contain any big novelty but it showcases common methods to find superfunctions by hand.

Let

$$
p(x)=\frac{ax+b}{x+c}.
$$

This describes all ratios of linear functions, while ignoring linear functions, which are simpler to treat. Let's define the $j$th composition of this function as

$$
p_j(x)=\frac{a_jx+b_j}{k_jx+c_j}
$$

This form of function can be guessed from doing some composition. We could get rid of $k_j$ but it would complicate the computation.
We know that

$$
p_{j+1}(x)=p(p_j(x))=\frac{a_jax+b_jx+a_jb+b_jc}{k_jax+c_jx+bk_j+cc_j}
$$

Meaning that

$$
\left\{
	\begin{array}{ll}
	  a_{j+1}=a_ja+b_j\\
	  b_{j+1}=a_jb+b_jc\\
	  c_{j+1}=bk_j+cc_j\\
	  k_{j+1}=k_ja+c_j
	\end{array}
\right.
$$

Which is equivalent to two systems of equations:

$$
\begin{pmatrix}a_{j+1}\\b_{j+1}\end{pmatrix}
=\begin{pmatrix}a&1\\b&c\end{pmatrix}
\begin{pmatrix}a_{j}\\b_{j}\end{pmatrix}
$$

$$
\begin{pmatrix}c_{j+1}\\k_{j+1}\end{pmatrix}
=\begin{pmatrix}c&b\\1&a\end{pmatrix}
\begin{pmatrix}c_{j}\\k_{j}\end{pmatrix}
$$

with initial conditions

$$
\begin{pmatrix}c_{0}\\k_{0}\end{pmatrix}=
\begin{pmatrix}a_{0}\\b_{0}\end{pmatrix}=
\begin{pmatrix}1\\0\end{pmatrix}
$$

as $p_0(x)=x$, the identity function.
We now want to find

$$
M_1^n=\begin{pmatrix}a&1\\b&c\end{pmatrix}^n
$$

$$
M_2^n=\begin{pmatrix}c&b\\1&a\end{pmatrix}^n
$$

by diagonalisation, this is equivalent to

$$
M_{1/2}^n=S_{1/2}J_{1/2}^nS_{1/2}^{-1}
$$

with $J_{1/2}$ containing the eigenvalues of $M_{1/2}$ and $S_{1/2}$ containing its eigenvectors.
We are in fact only interested to the first column of $M_{1/2}^n$ as it will be multiplied by $\begin{pmatrix} 1 \\ 0 \end{pmatrix}$.

The result is

$$
\left\{
	\begin{array}{ll}
	  a_{j}=\frac{c-a+\sqrt{\rho}}{2\sqrt{\rho}}\left(\frac{a+c-\sqrt{\rho}}{2}\right)^j+\frac{a-c+\sqrt{\rho}}{2\sqrt{\rho}}\left(\frac{a+c+\sqrt{\rho}}{2}\right)^j\\
	  b_{j}=\frac{b}{\sqrt{\rho}}\left(\left(\frac{a+c+\sqrt{\rho}}{2}\right)^j-\left(\frac{a+c-\sqrt{\rho}}{2}\right)^j\right)\\
	  c_{j}=\frac{a-c+\sqrt{\rho}}{2\sqrt{\rho}}\left(\frac{a+c-\sqrt{\rho}}{2}\right)^j+\frac{c-a+\sqrt{\rho}}{2\sqrt{\rho}}\left(\frac{a+c+\sqrt{\rho}}{2}\right)^j\\
	  k_{j}=\frac{1}{\sqrt{\rho}}\left(\left(\frac{a+c+\sqrt{\rho}}{2}\right)^j-\left(\frac{a+c-\sqrt{\rho}}{2}\right)^j\right)\\
	\end{array}
\right.
$$

with

$$
\rho=(a-c)^2+4b
$$

Let now

$$
p_j(x)=\frac{A_jx+B_j}{x+C_j}
$$

which leads to

$$
\left\{
	\begin{array}{ll}
	  A_j=\frac{a_j}{k_j}=\frac{(c-a+\sqrt{\rho})(a+c-\sqrt{\rho})^j+(a-c+\sqrt{\rho})(a+c+\sqrt{\rho})^j}{2((a+c+\sqrt{\rho})^j-(a+c-\sqrt{\rho})^j)}\\
	  B_j=\frac{b_j}{k_j}=b\\
	  C_j=\frac{c_j}{k_j}=\frac{(a-c+\sqrt{\rho})(a+c-\sqrt{\rho})^j+(c-a+\sqrt{\rho})(a+c+\sqrt{\rho})^j}{2((a+c+\sqrt{\rho})^j-(a+c-\sqrt{\rho})^j)}\\
	\end{array}
\right.
$$