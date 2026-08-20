- Ha egy $a_{n}$ számsorozat bármely tagjához egy d valós számot hozzáadva a következő tagot kapjuk, akkor egy számtani sorozatnak nevezzük.
- Ezt a d számot differenciálnak nevezzük (latinul: különbség).
- Ha $(a_{n})$ egy számtani sorozat, akkor: 
$$
\begin{align}
a_{1} = 1 \\
a_{2} = a_{1} + d \\
a_{3} = a_{2} + d  \\
a_{n} = a_{1} + (n-1)\cdot d
\end{align}
$$
- Nevét onnan kapta, hogy érvényesülnek rá bizonyos számtani-közép-tulajdonságok:
	1. a második tagtól kezdve minden tag az őt közrefogó két tag számtani közepe: $$
a_{n} = \frac{ a_{n-1} + a_{n+1} }{2}
$$
	2. a második tagtól kezdve minden tag a rá szimmetrikusan elhelyezkedő két tag számtani közepe: $$
a_{n} = \frac{ a_{n-k} + a_{n+k} }{2}
$$
	3. egymást követő páratlan számú tag számtani közepe a középső tag: $$
a_{n} = \frac{a_{n-k} + a_{n-k+1} + \dots + a_{n} + \dots + a_{n+k-1} + a_{n+k}}{2k+1}
$$

- Tétel: $S_{n} = \frac{a_{1} + a_{n}}{2} \cdot n$ (1-től n-ig a sorozat tagjainak összege)
- Bizonyítás: $$ \begin{align}

S_{n} = a_{1} + a_{2} + a_{3} + \dots + a_{n} = a_{1} + (a_{1} +d) + (a_{2}+2d) + \dots + (a_{1} + (n-1)d) \\
 S_{n} = a_{n} + a_{n-1} + \dots + a_{2} + a_{1} = a_{n} + (a_{n}-d) + (a_{n} - 2d) + \dots + (a_{n} - (n-1)d)
 \end{align} 
$$
$$ \begin{align}
2S_{n} = (a_{1} + a_{n}) \cdot n  \\  \\

S_{n} = \frac{(a_{1} + a_{n})}{2} \cdot n
\end{align}
$$
