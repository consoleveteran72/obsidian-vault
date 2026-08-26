
## Műveletek közötti összefüggések

- Ha **alap és kitevő** ismert $\rightarrow$ **hatványozás**
- Ha **hatvány és kitevő** ismert $\rightarrow$ **gyökvonás**
- Ha **hatvány és alap** ismert $\rightarrow$ **logaritmus**

---

## N-edik gyök definíciója

Legyen $n$ 1-nél nagyobb egész szám, $a$ pedig valós szám.

> [!abstract] Definíció
> Legyen $\sqrt[n]{a}$ kifejezés értéke az a (páros $n$ esetén nem-negatív) szám, melynek $n$-edik hatványa az $a$ szám.
> 
> - **$a$**: alap
> - **$n$**: gyökkitevő

### Kikötések és feltételek:

- **Ha $n$ páros** ($n = 2k, k \in \mathbb{Z}$), akkor:
  $$\sqrt[n]{a} \ge 0 \quad \text{és} \quad a \ge 0$$
  
  *Példa az egyértelműségre:*
  $$\sqrt{4} \text{ lehetne } -2 \text{ és } 2 \text{ is, mert } (-2)^2 = 4 \text{ és } 2^2 = 4$$
  > [!warning] EGYÉRTELMŰSÉG!
  > Csak a **pozitívat** vesszük figyelembe!

- **Ha $n$ páratlan** ($n = 2k + 1, k \in \mathbb{Z}$), akkor:
  - **Nincs kikötés** (a gyök értéke lehet pozitív, $0$, negatív, és az alap is).

---

## Összefüggés a hatványozással

Definíció szerint:
$$\left(\sqrt[n]{a}\right)^n = a$$

Továbbá:
$$\left(a^{\frac{1}{n}}\right)^n = a$$

Tehát az $n$-edik gyököt tekinthetjük úgy, mint **$\frac{1}{n}$-edik hatványt**.

*Példák törtkitevőre:*
- $\sqrt{a} = a^{\frac{1}{2}}$
- $\sqrt[3]{b} = b^{\frac{1}{3}}$
- $\sqrt[4]{c^3} = c^{\frac{3}{4}}$

### Gyökvonás páros/páratlan kitevő esetén

> [!important] ABSZOLÚT ÉRTÉK!
> - **Páros gyökkitevőnél:**
>   $$\sqrt[n]{a^n} = |a|$$
>   *Példa:* $\sqrt[4]{(-3)^4} = \sqrt[4]{81} = 3$
>
> - **Páratlan gyökkitevőnél:**
>   $$\sqrt[n]{a^n} = a$$
>   *Példa:* $\sqrt[3]{(-3)^3} = \sqrt[3]{-27} = -3$

*(Egyenlet példa: $x^2 = 4 \Rightarrow |x| = 2 \Rightarrow x = 2 \text{ vagy } x = -2$)*

---

## N-edik gyök azonosságai

*(Ezek az azonosságok négyzetgyökre is igazak)*

1. $$\sqrt[n]{a} \cdot \sqrt[n]{b} = \sqrt[n]{a \cdot b}$$

2. $$\frac{\sqrt[n]{a}}{\sqrt[n]{b}} = \sqrt[n]{\frac{a}{b}}$$

3. $$\sqrt[n]{a^k} = \left(\sqrt[n]{a}\right)^k$$

4. $$\sqrt[n]{\sqrt[m]{a}} = \sqrt[n \cdot m]{a}$$

5. $$\sqrt[n]{a^m} = \sqrt[n \cdot k]{a^{m \cdot k}}$$