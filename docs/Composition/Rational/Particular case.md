The general case only works if

$$
b\ne-\frac{(a-c)^2}{4}
$$

Using this, we have

$$
\begin{pmatrix}a\\k\end{pmatrix}_{j+1}
=\begin{pmatrix}a&b\\1&c\end{pmatrix}
\begin{pmatrix}a\\k\end{pmatrix}_j
$$

$$
\begin{pmatrix}a\\k\end{pmatrix}_j
=\begin{pmatrix}\frac{a-c}{2}&1\\1&0\end{pmatrix}\begin{pmatrix}\frac{a+c}{2}&1\\0&\frac{a+c}{2}\end{pmatrix}^j\begin{pmatrix}0&1\\1&\frac{c-a}{2}\end{pmatrix}\begin{pmatrix}1\\0\end{pmatrix}
$$

$$
\begin{pmatrix}a\\k\end{pmatrix}_j
=\begin{pmatrix}j\left(\frac{a+c}{2}\right)^{j-1}\left(\frac{a-c}{2}\right) +\left(\frac{a+c}{2}\right) \\ j\left(\frac{a+c}2\right)^{j-1}\end{pmatrix}
$$

Thus

$$
\frac{a_j}{k_j}=\frac{a(j+1)+(1-j)c}{2j}
$$

Doing a similar reasonment with $c$, we get

$$
\frac{c_j}{k_j}=\frac{a(1-j)+(1+j)c}{2j}
$$

Thus

$$
p_j(x)=\frac{\frac{(1+j)a+(1-j)c}{2j}x-\left(\frac{a-c}{2}\right)^2}{x+\frac{(1-j)a+(1+j)c}{2j}}
$$