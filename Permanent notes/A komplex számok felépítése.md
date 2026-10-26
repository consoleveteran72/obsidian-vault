Date: 2026-10-19
Tags: #linear-algebra #komplex-számok


Olyan testet szeretnénk találni, amely tartalmazza a valós számokat, és van benne egy $i$ elem, amelyre $i^2 = -1$. Mivel $-1$ semelyik valós számnak sem a négyzete, ezért biztos egy bővebb testet keresünk mint $\mathbb{R}$. Ha ilyen test létezik, akkor a szokásos számolási szabályokból kényszerűen következik, hogy

$$
\begin{aligned}
(a + bi) + (c + di) &= (a + c) + (b + d)i, \\
(a + bi) - (c + di) &= (a - c) + (b - d)i, \\
(a + bi)(c + di) &= (ac - bd) + (ad + bc)i,
\end{aligned}
$$

hiszen $i^2 = -1$. Nemnulla $a + bi$ esetén pedig

$$
(a + bi)^{-1} = \frac{1}{a + bi} \cdot \frac{a - bi}{a - bi} = \frac{a - bi}{a^2 + b^2} = \frac{a}{a^2 + b^2} + \frac{-b}{a^2 + b^2}i.
$$

Itt $a^2 + b^2 > 0$, ha $(a, b) \neq (0, 0)$, ezért a nevező valóban nem nulla.

**3. Tétel.** Ha $a + bi = c + di$, ahol $a, b, c, d \in \mathbb{R}$, akkor $a = c$ és $b = d$.

**Bizonyítás.** Az egyenlet átrendezésével $(a - c) = -(b - d)i$ adódik. Négyzetre emelve $(a - c)^2 = -(b - d)^2$, vagyis két valós négyzet összege nulla; ebből $a - c = b - d = 0$ következik $\square$.

Tehát, ha a keresett test létezik, akkor az elemeinek összeadása, kivonása, szorzása és reciproka nem lehet más, mint a fenti képletekben. Most ezekkel a képletekkel meg is építjük.


Related concepts:
[[Index - Lineáris algebra]]
[[Test fogalma]]


Source:
