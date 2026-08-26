
Legyen $ABC\triangle$ derékszögű, $a, b$ befogókkal és $c$ átfogóval, ekkor:
$$a^2 + b^2 = c^2$$

> [!note] Megjegyzés (Megfordítás)
> Ha egy háromszögben teljesül, hogy $a^2 + b^2 = c^2$, akkor a háromszög derékszögű.

---

### Bizonyítás 1. (Területmódszerrel)

A két azonos oldalélű ($a+b$) négyzet területének egyenlőségéből:

$$T_{\text{bal}} = T_{\text{jobb}}$$
$$a^2 + b^2 + 4 \cdot \frac{a \cdot b}{2} = 4 \cdot \frac{a \cdot b}{2} + c^2$$

A mindkét oldalon szereplő $4 \cdot \frac{a \cdot b}{2}$ tagot kivonva:
$$a^2 + b^2 = c^2$$

---

### Bizonyítás 2. (Hasonlósággal)

Bontsuk fel az $ABC\triangle$-et az átfogóhoz tartozó $m_c$ magassággal két kisebb háromszögre ($T_1$ és $T_2$ területűekre).

A szögek egyenlősége miatt mindkét kis háromszög hasonló az eredeti nagy háromszöghöz:
$$ACM_c\triangle \sim BCM_c\triangle \sim ABC\triangle$$

* **Hasonlósági arány $ACM_c\triangle$ és $ABC\triangle$ esetén:**
  $$k_1 = \frac{b}{c}$$

* **Hasonlósági arány $BCM_c\triangle$ és $ABC\triangle$ esetén:**
  $$k_2 = \frac{a}{c}$$

A területek aránya a hasonlósági arány négyzete:
$$\frac{T_1}{T} = k_1^2 = \left(\frac{b}{c}\right)^2 \quad \text{és} \quad \frac{T_2}{T} = k_2^2 = \left(\frac{a}{c}\right)^2$$

Mivel $T_1 + T_2 = T$, osszuk el mindkét oldalt $T$-vel:
$$\frac{T_1}{T} + \frac{T_2}{T} = 1$$

Behelyettesítve a hasonlósági arányokat:
$$\left(\frac{a}{c}\right)^2 + \left(\frac{b}{c}\right)^2 = 1 \implies \frac{a^2 + b^2}{c^2} = 1 \implies a^2 + b^2 = c^2$$

---

### A Pithagorasz-tétel megfordításának bizonyítása

**TFH (Tegyük fel, hogy)** egy háromszögben $a^2 + b^2 = c^2$.

Vegyünk fel egy $DEF$ derékszögű háromszöget $a$ és $b$ befogókkal (legyen az átfogója $c'$).

Itt teljesül a Pithagorasz-tétel, azaz:
$$a^2 + b^2 = (c')^2$$

Mivel a feltétel szerint $a^2 + b^2 = c^2$, ezért:
$$c^2 = (c')^2 \implies c = c'$$

$$\implies ABC\triangle \text{ és } DEF\triangle \text{ egybevágó} \implies BCA\angle = 90^\circ$$