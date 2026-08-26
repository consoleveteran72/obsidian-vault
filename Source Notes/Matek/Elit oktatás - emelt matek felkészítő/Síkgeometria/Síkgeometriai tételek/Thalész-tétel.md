
Egy kör $AB$ átmérője a körvonal egy $C$ pontjából ($C \neq A, B$) mindig derékszögben látszik.

> [!note] Megjegyzés
> Egy derékszögű háromszög köré írható kör középpontja éppen az átfogó felezéspontja.

---

### Bizonyítás (Direkt irány)

$$2\alpha + 2\beta = 180^\circ \implies \alpha + \beta = 90^\circ$$

Mivel $OB = OA = OC = r$, ezért az $AOC\triangle$ és a $BOC\triangle$ egyenlő szárú háromszögek.

$$\implies CAO\angle = ACO\angle = 90^\circ - \beta$$
$$\implies OCB\angle = OBC\angle = 90^\circ - \alpha$$

$$\implies ACB\angle = ACO\angle + OCB\angle = (90^\circ - \beta) + (90^\circ - \alpha) = 180^\circ - (\alpha + \beta) = 90^\circ$$

---

### Vissza irány (Bizonyítás)

**F** legyen az $AB$ átfogó felezéspontja.  
Tükrözzük az $ABC\triangle$-t $F$-re középpontosan!

A középpontos tükrözés egy egybevágósági transzformáció (TR.), azaz:
* $B'C'A'\angle = 90^\circ$
* $BAC\angle = AB C'\angle$
* $ABC\angle = B A C'\angle$
* $(\alpha + \beta = 90^\circ\text{!})$

$$\implies ACBC' \text{ egy téglalap}$$

Azaz az átlók metszéspontja a köré írt kör középpontja. $\blacksquare$