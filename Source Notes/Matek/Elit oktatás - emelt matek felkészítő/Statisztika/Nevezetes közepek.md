
## Definíciók (Két nemnegatív számra)

Adott két pozitív szám: $a$ és $b$.

- **Számtani (aritmetikai) közép:**
  $$A = \frac{a + b}{2}$$

- **Mértani (geometriai) közép:**
  $$G = \sqrt{a b}$$

- **Harmonikus (reciprokos) közép:**
  $$H = \frac{2}{\frac{1}{a} + \frac{1}{b}}$$

- **Négyzetes (kvadratikus) közép:**
  $$Q = \sqrt{\frac{a^2 + b^2}{2}}$$

---

## Nevezetes Közepek Közötti Egyenlőtlenség

$$H \le G \le A \le Q$$

- **Feltétel:** Mindegyik egyszerre csak akkor létezik, ha $a, b > 0$.
- **Egyenlőség:** $H = G = A = Q$ csak akkor teljesül, ha $a = b$.

---

## Bizonyítás: Mértani és Számtani Közép Közötti Egyenlőtlenség ($G \le A$)

Azt igazoljuk, hogy $\sqrt{a b} \le \frac{a + b}{2}$:

1. **Négyzetre emelés** (mivel mindkét oldal nemnegatív):
   $$(\sqrt{a b})^2 \le \left(\frac{a + b}{2}\right)^2$$
   $$a b \le \frac{a^2 + 2a b + b^2}{4}$$

2. **Szorzás 4-gyel:**
   $$4a b \le a^2 + 2a b + b^2$$

3. **Rendezés (4ab kivonása mindkét oldalból):**
   $$0 \le a^2 - 2a b + b^2$$

4. **Teljes négyzetté alakítás:**
   $$0 \le (a - b)^2$$

Mivel egy valós szám négyzete mindig nemnegatív ($0 \le (a - b)^2$), az eredeti állítás is igaz minden pozitív $a, b$ számra. Az egyenlőség pontosan akkor áll fenn, ha $a - b = 0$, azaz $a = b$.