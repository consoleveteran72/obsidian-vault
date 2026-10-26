Date: 2026-10-19
Tags: #linear-algebra #komplex-számok #számhalmaz #definíció

## Definíció: 

$$
\mathbb{C} := \mathbb{R} \times \mathbb{R}
$$

az összes valós számpár halmaza. Definiáljuk a műveleteket az alábbi módon:

$$
\begin{aligned}
(a, b) + (c, d) &:= (a + c, b + d), \\
-(a, b) &:= (-a, -b), \\
(a, b)(c, d) &:= (ac - bd, ad + bc), \\
(a, b)^{-1} &:= \left(\frac{a}{a^2 + b^2}, \frac{-b}{a^2 + b^2}\right) \quad ((a, b) \neq (0, 0)).
\end{aligned}
$$

A $0$ komplex szám legyen $(0, 0)$, az $1$ pedig $(1, 0)$. A valós $a$-t a továbbiakban az $(0, a)$ helyett $(a, 0)$ komplex számmal azonosítjuk, és $i := (0, 1)$. Ekkor

$$
a + bi = (a, 0) + (b, 0)(0, 1) = (a, 0) + (0, b) = (a, b),
$$

azaz az $(a, b)$ pár helyett $a + bi$-t írhatunk.



Related concepts:
[[Index - Lineáris algebra]]
[[A komplex számok felépítése]]


Source:
