
## Hatványfogalom

Legyen egy $a \in \mathbb{R}$, $n$ pedig egy pozitív egész szám.

Ekkor $a^n$ azt az "$n$" tényezős szorzatot jelenti, melynek mindegyik tényezője az "$a$" szám.

- $a^2 = a \cdot a$
- $a^3 = a \cdot a \cdot a$
- $a^n = \underbrace{a \cdot a \cdot a \cdot a \dots a}_{n \text{ db}}$

> [!info] Hatvány elemei ($a^n$)
> - **$a$**: alap
> - **$n$**: kitevő
> - **$a^n$**: hatvány

Ha $n = 1$, akkor az $a^1$ kifejezést úgy értelmezzük, mintha az "$a$"-t igazából nem szoroznánk össze semmivel:
> [!important]
> $$a^1 = a$$

---

## Hatványozás azonosságai

### 1) Azonos alapú hatványok szorzása
> [!abstract] Azonosság
> $$a^n \cdot a^m = a^{n+m}$$

**Bizonyítás:**
$$\underbrace{(a \cdot a \cdot a \cdot a \dots a)}_{n \text{ db}} \cdot \underbrace{(a \cdot a \cdot a \dots a)}_{m \text{ db}} = \underbrace{a \cdot a \cdot a \cdot a \cdot a \dots a}_{n+m \text{ db}} = a^{n+m} \quad \checkmark$$

*Példa:*
$$2^8 \cdot 2^5 = 2^{13}$$

---

### 2) Azonos alapú hatványok osztása
> [!abstract] Azonosság
> $$\frac{a^n}{a^m} = a^{n-m} \quad (a \neq 0, n > m)$$

**Bizonyítás:**
$$\frac{\overbrace{a \cdot a \cdot a \dots a}^{n \text{ db}}}{\underbrace{a \cdot a \cdot a \dots a}_{m \text{ db}}} = a^{n-m} \quad \checkmark$$

*Példa:*
$$\frac{2^8}{2^5} = 2^3$$

---

### 3) Azonos kitevőjű hatványok szorzása
> [!abstract] Azonosság
> $$a^n \cdot b^n = (a \cdot b)^n$$

**Bizonyítás:**
$$\underbrace{(a \cdot a \cdot a \dots a)}_{n \text{ db}} \cdot \underbrace{(b \cdot b \cdot b \dots b)}_{n \text{ db}}$$
$$\stackrel{\text{komm.}}{=} a \cdot b \cdot a \cdot b \cdot a \cdot b \cdot a \cdot b \dots$$
$$\stackrel{\text{assoc.}}{=} \underbrace{(a \cdot b) \cdot (a \cdot b) \cdot (a \cdot b) \cdot (a \cdot b) \dots}_{n \text{ db}} = (a \cdot b)^n \quad \checkmark$$

---

### 4) Azonos kitevőjű hatványok osztása
> [!abstract] Azonosság
> $$\frac{a^n}{b^n} = \left(\frac{a}{b}\right)^n$$

**Bizonyítás:**
$$\frac{\overbrace{a \cdot a \cdot a \cdot a \dots a}^{n \text{ db}}}{\underbrace{b \cdot b \cdot b \cdot b \dots b}_{n \text{ db}}} \stackrel{\text{assoc.}}{=} \underbrace{\left(\frac{a}{b}\right) \cdot \left(\frac{a}{b}\right) \cdot \left(\frac{a}{b}\right) \cdot \left(\frac{a}{b}\right) \dots \left(\frac{a}{b}\right)}_{n \text{ db}} = \left(\frac{a}{b}\right)^n$$

---

### 5) Hatvány hatványozása
> [!abstract] Azonosság
> $$(a^n)^m = a^{n \cdot m}$$

**Bizonyítás:**
$$\underbrace{\left(\underbrace{a \cdot a \cdot a \cdot a \dots a}_{n \text{ db}}\right)^m}_{m \text{ db}} = \underbrace{\left(\underbrace{a \cdot a \cdot a \cdot a \dots a}_{n \text{ db}}\right) \cdot (\ \ ) \cdot (\ \ ) \cdot (\ \ ) \cdot (\ \ )}_{m \text{ db}} = a^{n \cdot m} \quad \checkmark$$