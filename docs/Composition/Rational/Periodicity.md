For a periodic composition, we want

$$
p_n(x)=x
$$

and thus, keeping our conventions from the general case, we want

$$
\frac{a_nx+bk_n}{k_nx+c_n}=x
$$

$$
\left\{
	\begin{array}{ll}
	  a_n=c_{n}\\
	  k_{n}=0
	\end{array}
\right.
$$

One can check that the second condition is sufficient for the first one to be satisfied so we will only considere this one. This second equations is equivalent to

$$
\left(a+c+\sqrt{\rho}\right)^n=\left(a+c-\sqrt{\rho}\right)^n
$$

which is equivalent to

$$
\left(1+\frac {\sqrt{\rho}} {a+c}\right)^n=\left(1-\frac {\sqrt{\rho}}{a+c}\right)^n
$$

except that it eliminates the solution $c=-a$, which is a solution of period 2. To continue, we can pose $z=\frac{\rho}{(a+c)^2}$ and apply the binomial theorem:

$$
\sum_{i=0}^j \begin{pmatrix}j\\i\end{pmatrix} z^{\frac{i-1}{2}}=\sum_{i=0}^j \begin{pmatrix}j\\i\end{pmatrix} (-1)^{i}z^{\frac{i-1}{2}}.
$$

Let $i=2m+1$ and $k=j-1$, we finally have

$$
\sum_{m=0}^{\lfloor\frac{k}{2}\rfloor}\frac{k!}{(2m+1)!(k-2m)!}z^m=0.
$$

Finding solutions in z, we can go back to the rational function via

$$
b=\frac{(z-1)(a^2+c^2)}{4}+\frac{(z+1)ac}{2}.
$$

Here is a list of solutions for z:

| Period |        | z   |     |     |     |     |
| ------ | ------ | --- | --- | --- | --- | --- |
| 1      |        | 1   |     |     |     |     |
| 2      | $a=-c$ | 1   |     |     |     |     |
| 3      |        | 1   | -3  |     |     |     |
| 4      | $a=-c$ | 1   |     | -1  |     |     |
| 5      |        | 1   |     |     |  $\pm2\sqrt{5}-5$   |     |
| 6      | $a=-c$ | 1   | -3  |     |     |  $-\frac 13$   |

Following solutions can be computed but they become complicated very fast. Also from a certain point, it asks to solve a polynomial of degree of 5 or more, even taking into account solutions that we get from sub-periods.

This is, as far as I know, a complete description of the periodicity of composition of rational linear functions.