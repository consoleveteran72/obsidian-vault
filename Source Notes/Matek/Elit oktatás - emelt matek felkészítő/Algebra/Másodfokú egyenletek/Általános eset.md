
$a \neq 0$, $b, c$ valós számok esetén $ax^2 + bx + c$ kifejezést **másodfokú kifejezésnek** nevezzük.

---

## ÁLTALÁNOS ESET
$a \neq 0, b \neq 0, c \neq 0 : ax^2 + bx + c = 0$ kifejezést kell megoldani

### 1. Két elsőfokú polinom szorzataként felírható
**Példa:**
$$x^2 + 4x + 3 = (x + 1)(x + 3) = 0$$
$$\Downarrow \quad \quad \Downarrow$$
$$x = -1 \quad x = -3$$

---

### 2. Elsőfokú polinom négyzeteként és egy számnak az összegeként felírható
**Példák:**
- $x^2 + 4x + 3 = (x + 2)^2 - 1 \implies (x + 2)^2 = 1 \implies |x + 2| = 1 \implies x + 2 = \pm 1$
- $5x^2 - 4\sqrt{5}x + 7 = (\sqrt{5}x - 2)^2 + 3 = 0$
  $$(\sqrt{5}x - 2)^2 = -3 \quad \text{⚡ (nincs valós megoldás)}$$

---

### 3. Megoldóképlet alkalmazása

**Tétel:** $ax^2 + bx + c = 0$ megoldóképlete:
$$x_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

**Bizonyítás:**
$$ax^2 + bx + c = 0 \quad / \cdot 4a$$
$$4a^2x^2 + 4abx + 4ac = 0$$
$$(2ax + b)^2 - b^2 + 4ac = 0$$
$$(2ax + b)^2 = b^2 - 4ac$$
$$|2ax + b| = \sqrt{b^2 - 4ac}$$
$$2ax + b = \pm \sqrt{b^2 - 4ac}$$
$$2ax = -b \pm \sqrt{b^2 - 4ac}$$
$$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

---

### Diszkrimináns ($D$)
$$D = b^2 - 4ac$$

- **$D > 0$**: 2 megoldás
- **$D = 0$**: 1 megoldás
- **$D < 0$**: 0 megoldás