Let

$$
P_n=(t+i\sqrt{1-t^2})^n=T_n+U_{n-1}i\sqrt{1-t^2}.
$$

+ $P_{n+2}=2tP_{n+1}-P_n$
	
$$
\displaylines{
\left(t+i\sqrt{1-t^2}\right)^{n+2}=2t\left(t+i\sqrt{1-t^2}\right)^{n+1}-\left(t+i\sqrt{1-t^2}\right)^{n}\\
\left(t+i\sqrt{1-t^2}\right)^{2}=2t\left(t+i\sqrt{1-t^2}\right)-1\\
t^2-1+t^2+2ti\sqrt{1-t^2}=2t^2-1+2ti\sqrt{1-t^2}
}
$$
 
+ $n^2P_n-tP_n'+(1-t^2)P_n''=0$


Some well-known hypothesis: 

$$
(1) n^2T_n-tP_n'+\left(1-t^2\right)T_n''=0
$$

$$
(2) \left(1-t^2\right)U_{n-1}''-3tU_{n-1}'+\left(n^2-1\right)U_{n-1}=0
$$

Now the proof:

$$
\displaylines{
n^2P_n-tP_n'+\left(1-t^2\right)P_n''\\
=n^2\left(T_n+U_{n-1}i\sqrt{1-t^2}\right)-t\left(T_n'+U_{n-1}'\sqrt{1-t^2}i-\frac{tU_{n-1}}{\sqrt{1-t^2}}i\right)\\
-\left(t^2-1\right)\left(T_n''+U_{n-1}''i\sqrt{1-t^2}-\frac{2tU_{n-1}'}{\sqrt{1-t^2}}-\frac{U_{n-1}}{\sqrt{(1-t^2)^3}}\right)\\
=\overbrace{\left(n^2T_n-tT_n'+\left(1-t^2\right)T_n''\right)}^{0\text{ by }(1)}+U_{n-1}i\left(n^2\sqrt{1-t^2}+\frac{t^2}{\sqrt{1-t^2}}+\frac{t^2-1}{\sqrt{(1--t^2)^3}}\right)\\
-U_{n-1}'i\left(t\sqrt{1-t^2}-\frac{2t}{\sqrt{1-t^2}}\left(t^2-1\right)\right)-U_{n-1}''i\sqrt{1-t^2}\left(t^2-1\right)\\
=\frac{i}{\sqrt{1-t^2}}\left(\left(n^2\left(1-t^2\right)+t^2-1\right)U_{n-1}-\left(t\left(1-t^2\right)+2t\left(1-t^2\right)\right)U_{n-1}'+(1-t^2)^2U_{n-1}''\right)\\
=i\sqrt{1-t^2}\left(\left(n^2-1\right)U_{n-1}U_{n-1}-3tU_{n-1}'+\left(1-t^2\right)U_{n-1}''\right)\\
=0 \text{ by (2)}
}
$$

Those properties are shared with $T_n$. The only thing that differentiates them is the initial conditions.