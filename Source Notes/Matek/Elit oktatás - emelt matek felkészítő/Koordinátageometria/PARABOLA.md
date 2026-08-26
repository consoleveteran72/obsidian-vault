
## Definíció

A parabola azon pontok halmaza a síkon, amelyek egy adott $v$ egyenestől (**vezéregyenes**) és egy $F \notin v$ ponttól (**fókuszpont**) **egyenlő távolságra** vannak.

---

## Egyenlet levezetése

Legyen a fókuszpont $F\left(0, \frac{p}{2}\right)$, a vezéregyenes egyenlete $v: y = -\frac{p}{2}$, a parabola egy pontja pedig $P(x_0, y_0)$.  
*(ahol $p$ a fókuszpont és a vezéregyenes távolsága)*

1. **Feltétel:**  
   $$d(F, P) = d(v, P) \implies |\vec{FP}| = d(v, P)$$

2. **Kifejezve a koordinátákkal:**  
   $$\sqrt{(x_0 - 0)^2 + \left(y_0 - \frac{p}{2}\right)^2} = y_0 - \left(-\frac{p}{2}\right)$$
   $$\sqrt{x_0^2 + y_0^2 - y_0 \cdot p + \frac{p^2}{4}} = y_0 + \frac{p}{2} \quad / ()^2$$

3. **Négyzetre emelés után:**  
   $$x_0^2 + \cancel{y_0^2} - y_0 \cdot p + \cancel{\frac{p^2}{4}} = \cancel{y_0^2} + y_0 \cdot p + \cancel{\frac{p^2}{4}}$$

4. **Egyszerűsítés:**  
   $$x_0^2 = 2y_0 \cdot p$$
  >[!important] 
  >$$\frac{1}{2p} \cdot x^2 = y$$

---

## Összefüggés az általános alakkal

Az $y = ax^2 + bx + c$ alakú parabolára:

- **Főegyüttható ($a$):**
  $$a = \frac{1}{2p}$$

- **Vezéregyenes és fókuszpont távolsága ($p$):**
  $$p = \frac{1}{2a}$$