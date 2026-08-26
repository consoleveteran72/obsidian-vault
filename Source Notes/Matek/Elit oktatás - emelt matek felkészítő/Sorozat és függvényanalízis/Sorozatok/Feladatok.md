
**Feladat:** $a_n = \frac{2n+4}{n+1}$

$$(a_n) = \left( \frac{6}{2}, \frac{8}{3}, \frac{10}{4}, \frac{12}{5}, \dots \right)$$

$$a_n \xrightarrow{?} 2$$

$a_n > 0 \implies K = 0$ (alsó korlát)

$K = ? \quad K = 3$ (felső korlát)

**Biz.:**
$$\frac{2n+4}{n+1} \le 3$$
$$2n+4 \le 3n+3$$
$$1 \le n \quad \checkmark$$

---

**Határérték számítás:**

$$\lim_{n \to \infty} \frac{2n+4}{n+1} \stackrel{\cdot \frac{1/n}{1/n}}{=} \lim_{n \to \infty} \frac{2\frac{n}{n} + \frac{4}{n}}{\frac{n}{n} + \frac{1}{n}} = \lim_{n \to \infty} \frac{2 + \frac{4}{n}}{1 + \frac{1}{n}}$$

Mivel $\frac{4}{n} \to 0$ és $\frac{1}{n} \to 0$:

$$= \frac{2}{1} = 2$$

---

**Monotonitás:**

$$a_n \le a_{n+1}$$
$$\frac{2n+4}{n+1} \le \frac{2(n+1)+4}{(n+1)+1}$$
$$\frac{2n+4}{n+1} \le \frac{2n+6}{n+2} \quad / \cdot (n+1)(n+2) > 0$$
$$(2n+4)(n+2) \le (2n+6)(n+1)$$
$$2n^2 + 4n + 4n + 8 \le 2n^2 + 6n + 2n + 6$$
$$8 > 6$$

$$\Downarrow$$

$$a_n > a_{n+1} \quad \implies \text{szigorúan monoton csökkenő (sz. m. cs.)}$$

$$\implies a_1 = \sup(a_n) = 3$$

**Áll.:**
$$\inf(a_n) = A = \lim_{n \to \infty} a_n = 2$$

---

**Küszöbindex számítás:**

$\varepsilon = \frac{1}{1000}$ hiba, $N = ?$ (küszöbindex)

*(„Az ördög által megadott $\frac{1}{1000}$-es hibához mekkora gyakorlási idő tartozik, ami után a hibán belül leszünk?”)*

$$|a_n - A| < \varepsilon$$
$$\left| \frac{2n+4}{n+1} - 2 \right| < \frac{1}{1000}$$
$$\left| \frac{2n+4 - 2(n+1)}{n+1} \right| < \frac{1}{1000}$$
$$\left| \frac{2}{n+1} \right| < \frac{1}{1000}$$

Mivel $n+1 > 0$ és $2 > 0$:

$$\frac{2}{n+1} < \frac{1}{1000}$$
$$2000 < n+1$$
$$1999 < n$$

$$\mathbf{N = 2000}$$