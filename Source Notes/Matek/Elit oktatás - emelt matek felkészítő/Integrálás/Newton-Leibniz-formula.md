
**Tétel (Newton–Leibniz-formula):**

Ha $f : [a, b] \to \mathbb{R}$ folytonos, akkor:

$$\int_{a}^{b} f(x) \, dx = F(b) - F(a)$$

ahol $F : [a, b] \to \mathbb{R}$ deriválható, és $F'(x) = f(x)$.

---

**Definíció (Primitív függvény / Határozatlan integrál):**

Ha $f : \mathbb{R} \to \mathbb{R}$ és $F : \mathbb{R} \to \mathbb{R}$ deriválható, valamint $F'(x) = f(x)$, akkor:

$$F(x) = \int f(x) \, dx$$

$F(x)$-et az $f(x)$ **primitív függvényének** (vagy határozatlan integráljának) nevezzük.

---

# ALAPINTEGRÁLOK (PÉLDÁK)

1. $$\int 0 \, dx = C \quad (\text{konstans fv.})$$
2. $$\int 1 \, dx = x + C$$
3. $$\int x \, dx = \frac{1}{2}x^2 + C$$
4. $$\int x^n \, dx = \frac{x^{n+1}}{n+1} + C \quad (n \neq -1)$$
   $$\left( \int x^{-1} \, dx = \int \frac{1}{x} \, dx = \ln x + C \right)$$
5. $$\int \cos x \, dx = \sin x + C$$
6. $$\int \sin x \, dx = -\cos x + C$$

---

# HATÁROZOTT INTEGRÁL PÉLDÁK

**1. Példa:**

$$\int_{0}^{1} x^2 \, dx = \left[ \frac{x^3}{3} \right]_{0}^{1} = \frac{1^3}{3} - \frac{0^3}{3} = \frac{1}{3}$$

**2. Példa:**

$$\int_{0}^{\pi} \sin x \, dx = [-\cos x]_{0}^{\pi} = -(-1) - (-1) = 2$$

**3. Példa (Előjeles terület illusztrációja):**

$$\text{Viszont: } \int_{0}^{2\pi} \sin x \, dx = [-\cos x]_{0}^{2\pi} = -1 - (-1) = 0$$

---

# KÉT FÜGGVÉNYGÖRBE KÖZÖTTI TERÜLET

Legyen $f, g : [a, b] \to \mathbb{R}$ folytonosak, és $f(x) \ge g(x) \quad \forall x \in [a, b]$.

Ekkor a két görbe közötti terület ($T$):

$$T = \int_{a}^{b} (f(x) - g(x)) \, dx$$