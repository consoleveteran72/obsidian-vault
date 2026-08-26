
**Jelölések:**
- $e$: egyenes
- $P(x_0, y_0) \in e$: az egyenes egy adott pontja
- $e \cap y\text{-tengely} = (0, b)$: az egyenes metszéspontja az $y$-tengellyel
- $\underline{v}[v_1, v_2] \parallel e$: irányvektor
- $\underline{n}[A, B] \perp e$: normálvektor
- $m_e = m_{\underline{v}} = \frac{v_2}{v_1}$: az egyenes meredeksége (iránytangense)

---

## Egyenes egyenletének alakjai

1. **Meredekséggel és $y$-metszettel:**
   $$y = m \cdot x + b$$

2. **Ismert $P(x_0, y_0)$ ponttal és $m$ meredekséggel:**
   $$y - y_0 = m(x - x_0)$$

   > **Megjegyzés (görbe érintője):**
   > Az $f(x)$ függvény görbéjének érintője az $x_0$ pont felett:
   > $$y - f(x_0) = f'(x_0)(x - x_0)$$
   > ahol $x_0 = x_0$, $y_0 = f(x_0)$ és $m = f'(x_0)$.

3. **Adott $P(x_0, y_0)$ pont és $\underline{v}[v_1, v_2]$ irányvektor esetén:**
   $$v_2 x - v_1 y = v_2 x_0 - v_1 y_0$$

4. **Adott $P(x_0, y_0)$ pont és $\underline{n}[A, B]$ normálvektor esetén:**
   $$Ax + By = Ax_0 + By_0$$

---

## Egyenesek párhuzamossága és merőlegessége

- **Párhuzamosság:**
  $$e \parallel f \iff m_e = m_f$$

- **Merőlegesség:**
  $$e \perp f \iff m_e \cdot m_f = -1 \iff m_f = -\frac{1}{m_e}$$