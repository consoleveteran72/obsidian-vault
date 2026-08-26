# RIEMANN-KÖZELÍTŐÖSSZEGEK

Legyen $f : [a, b] \to \mathbb{R}$ folytonos függvény.

Vegyünk egy $a < x_1 < x_2 < b$ úgynevezett **felosztást**:

* $f(x)$ az $[a, x_1]$-en $u_1$-ben a legkisebb, $v_1$-ben a legnagyobb értéket veszi fel.
* $[x_1, x_2]$-ben $u_2$-ben a legkisebb, $v_2$-ben a legnagyobb.
* $[x_2, x_3]$-ban $u_3$-ban a legkisebb, $v_3$-ban a legnagyobb.

---

Vegyünk egyre sűrűbb/finomabb felosztását $[a, b]$-nek. Ekkor:

* $I_*$ **alsó közelítő összegezés / összeg** *(az alsó téglalapok területösszege)*
* $I^*$ **felső közelítő összegezés / összeg** *(a felső téglalapok területösszege)*

Nyilvánvalóan:

$$I_* \le \int_{a}^{b} f(x) \, dx \le I^*$$

---

**Konvergencia és a határérték:**

Ha $I^* - I_* \to 0$, akkor:

$$\exists \int_{a}^{b} f(x) \, dx$$

és ez az $I^*$ határértéke, és az $I_*$ határértéke is egyben.