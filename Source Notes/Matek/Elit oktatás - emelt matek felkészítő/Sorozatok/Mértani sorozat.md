
- Ha egy számsorozat bármely tagját egy valós $q$ számmal megszorozva a sorozat következő tagját kapjuk, akkor **mértani sorozatról** beszélünk.
- A $q$ másnéven **quotient** ("kvóciens") (*latinul: hányados*).

- Ha $(a_n)$ egy mértani sorozat, akkor:
  $$a_1 = a_1$$
  $$a_2 = a_1 \cdot q$$
  $$a_3 = a_2 \cdot q = (a_1 \cdot q) \cdot q = a_1 \cdot q^2$$
  $$a_n = a_{n-1} \cdot q = a_1 \cdot q^{n-1}$$

> [!important] N-edik tag képlete
> $$a_n = a_1 \cdot q^{n-1}$$

---

> [!note] Mértani közép
> $$G(a, b) = \sqrt{a \cdot b}$$

Nevét onnan kapta, hogy érvényesülnek rá bizonyos mértani-közép-tulajdonságok:

1. Második tagtól kezdve minden tag abszolútértéke az őt közrefogó tagok mértani közepe:
   $$|a_n| = \sqrt{a_{n-1} \cdot a_{n+1}} = \sqrt{\frac{a_n}{q} \cdot a_n \cdot q} = \sqrt{a_n^2} = |a_n| \quad \checkmark$$

2. Második tagtól kezdve minden tag abszolútértéke a rá szimmetrikusan elhelyezkedő tagok mértani közepe:
   $$|a_n| = \sqrt{a_{n-k} \cdot a_{n+k}}$$

3. Páratlan számú egymást követő tag mértani közepe a középső tag:
   $$a_n = \sqrt{a_{n-k} \cdot a_{n-k+1} \cdot \space \dots \space \cdot a_n \cdot \space \dots \space \cdot a_{n+k}}$$

---

## Mértani sorozat első $n$ tagjának összege ($S_n$)

- Ha $q = 1$, akkor minden tag egyenlő az első taggal $\Rightarrow S_n = a_1 \cdot n$

- Ha $q \neq 1$:

> [!abstract] Tétel
> $$S_n = a_1 \cdot \frac{q^n - 1}{q - 1}$$

### Bizonyítás:

$$S_n = a_1 + a_2 + a_3 + \dots + a_n = a_1 + a_1 \cdot q + a_1 \cdot q^2 + \dots + a_1 \cdot q^{n-1}$$

$$q \cdot S_n = q \cdot a_1 + q \cdot a_2 + \dots + q \cdot a_n = a_1 \cdot q + a_1 \cdot q^2 + a_1 \cdot q^3 + \dots + a_1 \cdot q^n$$

Kivonva egymásból a két egyenletet ($q \cdot S_n - S_n$):

$$q \cdot S_n - S_n = a_1 \cdot q^n - a_1 = a_1(q^n - 1)$$
$$S_n(q - 1) = a_1 \cdot (q^n - 1)$$

$$S_n = a_1 \cdot \frac{q^n - 1}{q - 1}$$