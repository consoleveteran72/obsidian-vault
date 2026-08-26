# NÉHÁNY ELEMI FÜGGVÉNY DERIVÁLTJA

1. $$(x^n)' = n \cdot x^{n-1} \quad (n \in \mathbb{R})$$
2. $$(\sin x)' = \cos x$$
3. $$(\cos x)' = -\sin x$$

---

**Állítás:** Ha $n \in \mathbb{N}$, akkor $(x^n)' = n \cdot x^{n-1}$

**Bizonyítás:** 

Legyen $f(x) = x^n$, $x_0 \in \mathbb{R}$ fix.

$$f'(x_0) = \lim_{x \to x_0} \frac{f(x) - f(x_0)}{x - x_0} = \lim_{x \to x_0} \frac{x^n - x_0^n}{x - x_0} = (*)$$

---

**Kitérő (Algebrai azonosságok):**

* $a^1 - b^1 = a - b$
* $a^2 - b^2 = (a - b)(a + b)$
* $a^3 - b^3 = (a - b)(a^2 + ab + b^2)$
* $\vdots$
* $a^n - b^n = (a - b)(a^{n-1} + a^{n-2}b + \dots + a b^{n-2} + b^{n-1})$

Ebből átrendezve:

$$\frac{a^n - b^n}{a - b} = a^{n-1} + a^{n-2}b + \dots + a b^{n-2} + b^{n-1}$$

---

**Folytatás:**

$$(*) = \lim_{x \to x_0} \left( x^{n-1} + x^{n-2} x_0 + \dots + x x_0^{n-2} + x_0^{n-1} \right)$$

$$= x_0^{n-1} + \dots + x_0^{n-1} = n \cdot x_0^{n-1}$$

$$\implies (x^n)' = n \cdot x^{n-1}$$