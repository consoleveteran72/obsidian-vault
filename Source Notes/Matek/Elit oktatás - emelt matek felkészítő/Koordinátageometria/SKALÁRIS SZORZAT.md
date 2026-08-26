
## Definíciók és Alapösszefüggés

Adott két helyvektor: $\underline{a}(a_1, a_2)$ és $\underline{b}(b_1, b_2)$.

- **Eredeti definíció:**
  $$\underline{a} \cdot \underline{b} = |\underline{a}| \cdot |\underline{b}| \cdot \cos\varphi$$
  *(két vektor szorzata egy valós számot / skalárt ad eredményül)*

- **Kiszámítása koordinátákból (Definíció 2):**
  $$\underline{a} \cdot \underline{b} = a_1 b_1 + a_2 b_2$$

- **Tétel:**  
  $$|\underline{a}| \cdot |\underline{b}| \cdot \cos\varphi = \underline{a} \cdot \underline{b} = a_1 b_1 + a_2 b_2$$

- **Következmény (Szögszámítás koordinátákból):**
  $$\cos\varphi = \frac{a_1 b_1 + a_2 b_2}{\sqrt{a_1^2 + a_2^2} \cdot \sqrt{b_1^2 + b_2^2}}$$

---

## Tulajdonságok

1. **Kommutatív:** $\underline{a} \cdot \underline{b} = \underline{b} \cdot \underline{a}$
2. **Skalárral való szorzás:** $(r \cdot \underline{a}) \cdot \underline{b} = \underline{a} \cdot (r \cdot \underline{b}) = r \cdot (\underline{a} \cdot \underline{b}) \quad (r \in \mathbb{R})$
3. **Disztributív:** $(\underline{a} + \underline{b}) \cdot \underline{c} = \underline{a} \cdot \underline{c} + \underline{b} \cdot \underline{c}$
4. **Nullvektor / Merőlegesség:**
   $$\underline{a} \cdot \underline{b} = 0 \iff |\underline{a}| \cdot |\underline{b}| \cdot \cos\varphi = 0 \iff \begin{cases} \underline{a} = \underline{0} \\ \text{vagy} \\ \underline{b} = \underline{0} \\ \text{vagy} \\ \cos\varphi = 0 \iff \varphi = 90^\circ \iff \underline{a} \perp \underline{b} \end{cases}$$

---

## A Skaláris Szorzat Jele és a Bezárt Szög

- **Hegyesszög ($0^\circ < \varphi < 90^\circ$):**
  $$\underline{a} \cdot \underline{b} > 0 \iff \cos\varphi > 0$$

- **Tompaszög ($90^\circ < \varphi < 180^\circ$):**
  $$\underline{a} \cdot \underline{b} < 0 \iff \cos\varphi < 0$$

---

## A Koordinátás Alak Levezetése (Egységvektorokkal)

Legyen az $x$-tengely egységvektora $\underline{i} = [1, 0]$, a $y$-tengelyé $\underline{j} = [0, 1]$. Ekkor $\underline{a} = a_1 \underline{i} + a_2 \underline{j}$ és $\underline{b} = b_1 \underline{i} + b_2 \underline{j}$.

$$\underline{a} \cdot \underline{b} = (a_1 \underline{i} + a_2 \underline{j}) \cdot (b_1 \underline{i} + b_2 \underline{j})$$
$$= a_1 b_1 (\underline{i} \cdot \underline{i}) + a_1 b_2 (\underline{i} \cdot \underline{j}) + a_2 b_1 (\underline{j} \cdot \underline{i}) + a_2 b_2 (\underline{j} \cdot \underline{j})$$

Tudjuk, hogy:
- $\underline{i} \cdot \underline{i} = |\underline{i}| \cdot |\underline{i}| \cdot \cos 0^\circ = 1 \cdot 1 \cdot 1 = 1$
- $\underline{j} \cdot \underline{j} = |\underline{j}| \cdot |\underline{j}| \cdot \cos 0^\circ = 1 \cdot 1 \cdot 1 = 1$
- $\underline{i} \cdot \underline{j} = \underline{j} \cdot \underline{i} = |\underline{i}| \cdot |\underline{j}| \cdot \cos 90^\circ = 1 \cdot 1 \cdot 0 = 0$

Behelyettesítve:
$$\underline{a} \cdot \underline{b} = a_1 b_1 (1) + a_1 b_2 (0) + a_2 b_1 (0) + a_2 b_2 (1) = a_1 b_1 + a_2 b_2 \quad \blacksquare$$

---

## Kidolgozott Feladat (Példa)

**Kérdés:** Adott $\underline{a}[4, 2]$ és $\underline{b}[-2, -6]$. Mekkora a két vektor által bezárt $\varphi$ szög?

1. **Behelyettesítés az egyenlőségbe:**
   $$\sqrt{4^2 + 2^2} \cdot \sqrt{(-2)^2 + (-6)^2} \cdot \cos\varphi = 4 \cdot (-2) + 2 \cdot (-6)$$

2. **Számolás:**
   $$\sqrt{20} \cdot \sqrt{40} \cdot \cos\varphi = -8 - 12$$
   $$\sqrt{20} \cdot \sqrt{20} \cdot \sqrt{2} \cdot \cos\varphi = -20$$
   $$20 \cdot \sqrt{2} \cdot \cos\varphi = -20 \quad / : 20$$
   $$\sqrt{2} \cdot \cos\varphi = -1$$
   $$\cos\varphi = -\frac{1}{\sqrt{2}} \implies \varphi = 135^\circ$$