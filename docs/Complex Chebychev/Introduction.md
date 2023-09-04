An interesting way to study complex function is to consider them as a $R\rightarrow R^2$ function. Let $f$, a function defined over the complex numbers. We can then look at

$$
(t, \Re{[f(t)]}, \Im{[f(t)]})
$$

as a 3D plot. Doing so, some operation appear as well-known geometric operations over a whole function. For example, exponentiation leads to a rotation of the points and moves them away(closer) from the origin if they have a modulus bigger(smaller) than one. When one notices this, he could search for a function on which only the rotation is applied. This means a function which always has modulus 1.

In this case, the function looks like a coil and exponentiation makes the coil spin faster or slower.

The first solution which should come to mind should be

$$
g(t)=e^{it}
$$

with i, the imaginary number. One can see that this has modulus one. When exponentating, we will simply have

$$
g(t)^n=g(tn).
$$

This is an interesting but well-known function and I don't think I could say much about it that hasn't been heard a thousand time.


Let's take now take another function which fullfills the modulus one condition: 

$$
f(t,n)=\left(t+i\sqrt{1-t^2}\right)^n.
$$

Let's look at the values of the function for the first $n$'s.

| n   | f(t,n)                               |
| --- | ------------------------------------ |
| 0   | $1$                                 |
| 1   | $t+i\sqrt{1-t^2}$                    |
| 2   | $2t^2-1+2ti\sqrt{1-t^2}$             |
| 3   | $4t^3-3t+(4t^2-1)i\sqrt{1-t^2}$      |
| 4   | $8t^4-8t^2+1+(8t^3-4t)i\sqrt{1-t^2}$ |

Now, it should be obvious that for all integer $n$'s, the function takes the form 

$$
f(t,n)=T_n(t)+U_{n-1}(t)i\sqrt{1-t^2}
$$

with $T_n(t)$ and $U_n(t)$, polynomials in $t$.
Some of you will have directly recognised the Chebyshevs polynomyals (maybe hinted by my less than subtel choice of notation when descibing the form). If it wasn't obious to you, inputing the coeficients in the [OEIS](https://oeis.org/A028297) could have led you to this conclusion (as it had for me when I didn't know about Chebyshevs polynomyals).

We can prove that this is actually true. To do so let's take the change of variables $t=\cos u$. Then we have

$$
f(t,n)=\left(\cos u+i\sqrt{1-\cos^2u}\right)^n=\left(\cos u+i\sin u\right)^n= g(u)^n=g(un)
$$

Undoing the change of variable leads to 

$$
\displaylines{f(t,n)=g(n\arccos t)=\cos(n\arccos t)+i\frac{\sin(n\arccos t)}{\sin(\arccos t)}\sin(\arccos t)\\ =T_n(t)+iU_{n-1}(t)\sqrt{1-t^2}}
$$

where $T_n$ is the Chebyshev polynomial of the first kind and $U_n$, the Chebyshev polynomial of the second kind.