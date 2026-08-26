
Vegyünk fel egy $AB$ húrt a $K$ körön (középpontja $O$). Legyen $C$ az $AB$ egyik rögzített ívének pontja ($C \neq A, B$).

**Tétel:**  
Az $ACB\angle$ kerületi szög nem függ $C$ választásától (az adott íven), és a hozzá tartozó középponti szög a kerületi szög kétszerese:
$$AOB\angle = 2 \cdot ACB\angle$$

> [!note] Következmények (Köv.)
> 1. **Thalész-tétel:** ha $AB$ átmérő, akkor a középponti szög $180^\circ$, így a kerületi szög $90^\circ$.
> 2. Adott $AB$ szakasz és $\alpha$ szög esetén azon $C$ pontok helye a síkban, ahonnan $AB$ szakasz $\alpha$ szög alatt látszik: **2 db (látó)körív**.

---

### Bizonyítás (3 eset)

#### 1. Eset: $C, O, A$ egy egyenesen van
$$AOB\angle = 2\alpha \implies BOC\angle = 180^\circ - 2\alpha$$

Az $OCB\triangle$ egyenlő szárú ($OC = OB = r$), így:
$$OCB\angle = \frac{180^\circ - (180^\circ - 2\alpha)}{2} = \alpha \quad$$

---

#### 2. Eset: Az $ABC\triangle$ belső pontja az $O$ pont
Legyen rögzítve az $AOB\angle = 2\alpha$, továbbá legyen $AOC\angle = 2\gamma$ és $BOC\angle = 2\beta$.

A középponti szögek összege:
$$2\alpha + 2\beta + 2\gamma = 360^\circ \implies \alpha + \beta + \gamma = 180^\circ$$

Az $AOC\triangle$ egyenlő szárú $\implies CAO\angle = ACO\angle = 90^\circ - \gamma$  
A $BOC\triangle$ egyenlő szárú $\implies BCO\angle = CBO\angle = 90^\circ - \beta$

A teljes kerületi szög:
$$ACB\angle = ACO\angle + OCB\angle = (90^\circ - \gamma) + (90^\circ - \beta) = 180^\circ - (\gamma + \beta) = \alpha \quad$$

---

#### 3. Eset: Az $AOB\triangle$ nem tartalmazza a $C$ pontot
Legyen $AOB\angle = 2\alpha$ (rögzített) és $BOC\angle = 2\beta$.

* Az $OCB\triangle$ egyenlő szárú $\implies OCB\angle = 90^\circ - \beta$
* Az $ACO\triangle$ is egyenlő szárú, középponti szöge $2\alpha + 2\beta$:
  $$\implies OCA\angle = \frac{180^\circ - (2\alpha + 2\beta)}{2} = 90^\circ - \alpha - \beta$$

A keresett kerületi szög:
$$ACB\angle = OCB\angle - OCA\angle = (90^\circ - \beta) - (90^\circ - \alpha - \beta)$$
$$ACB\angle = 90^\circ - \beta - 90^\circ + \alpha + \beta = \alpha \quad$$