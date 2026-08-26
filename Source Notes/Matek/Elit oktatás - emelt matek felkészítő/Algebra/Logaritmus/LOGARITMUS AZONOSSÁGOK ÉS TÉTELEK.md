
## 1. 
$$\log_a x + \log_a y = \log_a (x \cdot y)$$

**Bizonyítás:**
Let $a^b = x$ és $a^c = y$

$$\log_a a^b + \log_a a^c = \log_a (a^b \cdot a^c)$$
$$b + c = \log_a a^{b+c}$$
$$b + c = b + c \quad \checkmark$$

---

## 2.
$$\log_a x - \log_a y = \log_a \left(\frac{x}{y}\right)$$

**Bizonyítás:**
$$\log_a a^b - \log_a a^c = \log_a \left(\frac{a^b}{a^c}\right)$$
$$b - c = \log_a a^{b-c}$$
$$b - c = b - c \quad \checkmark$$

---

## 3. 
$$\log_a x^n = n \cdot \log_a x$$

**Bizonyítás:**
Let $a^c = x$

$$\log_a (a^c)^n = n \cdot \log_a a^c$$
$$\log_a a^{c \cdot n} = n \cdot \log_a a^c$$
$$c \cdot n = n \cdot c \quad \checkmark$$

---

## TÉTELEK

### 4. Tétel (Kitevő az alapban)
$$\log_{a^n} x = \frac{1}{n} \cdot \log_a x \quad \text{és} \quad \log_{\sqrt[n]{a}} x = n \cdot \log_a x$$

---

### 5. Tétel: Más alapra való áttérés
$$\log_a b = \frac{\log_c b}{\log_c a}$$

**Bizonyítás / Levezetés:**
- $a^x = b$
- $c^y = b$
- $c^z = a$

$$\log_{c^z} c^y = \frac{\log_c c^y}{\log_c c^z} = \frac{y}{z}$$
$$\left(c^z\right)^{\frac{y}{z}} = c^y \implies c^y = c^y \quad \checkmark$$

**Példa:**
$$\text{pl. } \log_3 12 = \frac{\lg 12}{\lg 3}$$