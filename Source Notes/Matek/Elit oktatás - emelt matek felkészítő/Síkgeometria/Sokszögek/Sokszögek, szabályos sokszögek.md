
## Konvex n-szög

* **Külső szögek összege:** $360^\circ$
* **Belső szögek összege:** $(n - 2) \cdot 180^\circ$

Egy tetszőleges csúcsból $n - 3$ db átló húzható, ezzel $n - 2$ db háromszög keletkezik.  
A belső szögek összege így a keletkezett háromszögek belső szögeinek összege, azaz:
$$(n - 2) \cdot 180^\circ$$

---

### A külső szögek összegének bizonyítása ($360^\circ$)

Minden csúcsnál a belső szög ($\beta_i$) és a külső szög ($\alpha_i$) mellékszögek, így összegeik:

$$\begin{aligned}
\alpha_1 + \beta_1 &= 180^\circ \\
\alpha_2 + \beta_2 &= 180^\circ \\
&\;\;\vdots \\
\alpha_n + \beta_n &= 180^\circ
\end{aligned}$$

Adjuk össze az $n$ darab egyenletet:

$$(\alpha_1 + \alpha_2 + \dots + \alpha_n) + (\beta_1 + \beta_2 + \dots + \beta_n) = n \cdot 180^\circ$$

Helyettesítsük be a belső szögek összegét ($\beta_1 + \beta_2 + \dots + \beta_n = (n - 2) \cdot 180^\circ$):

$$(\alpha_1 + \alpha_2 + \dots + \alpha_n) + (n - 2) \cdot 180^\circ = n \cdot 180^\circ$$

Fejezzük ki a külső szögek összegét:

$$\alpha_1 + \alpha_2 + \dots + \alpha_n = n \cdot 180^\circ - (n - 2) \cdot 180^\circ$$

$$\alpha_1 + \alpha_2 + \dots + \alpha_n = n \cdot 180^\circ - n \cdot 180^\circ + 360^\circ$$

$$\alpha_1 + \alpha_2 + \dots + \alpha_n = 360^\circ$$