
## 1. Tétel (Érintő és sugarak viszonya)

**Állítás:** Egy kör középpontjából az érintési pontba húzott sugár merőleges az érintőre.

### Bizonyítás (Indirekt)

Tegyük fel, hogy $OE \not\perp e$.  
Legyen $T \in e$ az a pont, ahol $OT \perp e$.

* Az $OTE$ derékszögű háromszögben $x = OT$ befogó és $r = OE$ átfogó, így:
  $$x < r$$

* Mivel $E$ rajta van a körön, $T$ pedig a körön kívül van (mert $e$ érintő, így csak egyetlen közös pontja van a körrel), ezért:
  $$x > r$$

A két állítás ellentmond egymásnak ($x < r$ és $x > r$), így az eredeti feltevésünk hibás volt.  
$\implies OE \perp e$

---

## 2. Tétel (Körhöz húzott érintőszakaszok)

**Állítás:** Körhöz külső pontból húzott érintőszakaszok hossza egyenlő.
$$\text{Azaz: } PE_1 = PE_2$$

### Bizonyítás

A két derékszögű háromszög egybevágó:
$$OPE_1\triangle \cong OPE_2\triangle$$

Mivel:
* $OP$ oldaluk közös (átfogó)
* $OE_1 = OE_2 = r$ (befogók)
* $OE_1P\angle = OE_2P\angle = 90^\circ$

A háromszögek egybevágóságából következik:
$$\implies PE_1 = PE_2$$