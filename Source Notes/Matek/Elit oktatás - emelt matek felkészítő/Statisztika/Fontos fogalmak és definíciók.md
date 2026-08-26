# STATISZTIKA

## Alapfogalmak és Átlagok

- **Adatsokaság:** A vizsgált adatok halmaza.
- **Átlag ($\bar{X}$):** 
  $$\bar{X} = \frac{\text{adatok összege}}{\text{adatok száma}}$$
- **Súlyozott átlag:** Akkor használjuk, ha egyes adatok többször is előfordulnak (a gyakoriságuk a súly).

### Példa:
- **Példa adatsokaság:** $1, 5, 5, 4, 3, 2, 1, 1, 1, 2$
- **Súlyozott átlag számítása:**
  $$\text{Súlyozott átlag} = \frac{4 \cdot 1 + 2 \cdot 2 + 3 \cdot 1 + 2 \cdot 5}{10} = \frac{25}{10} = 2{,}5$$

---

## Egyesített Átlag

Ha két külön adatsokaságunk van:
- **I. adatsokaság:** $n$ elem, $A$ átlag
- **II. adatsokaság:** $m$ elem, $B$ átlag

Összevonva a két sokaságot, az **új (egyesített) átlag**:
$$\text{Új átlag} = \frac{n \cdot A + m \cdot B}{n + m}$$

---

## Gyakoriság és Relatív Gyakoriság

A fenti példa adatsokaságra ($1, 5, 5, 4, 3, 2, 1, 1, 1, 2$):

### Gyakorisági Táblázat
A **gyakoriság** megmutatja, hogy egy adott érték hányszor fordul elő a mintában.

| Érték          |  1  |  2  |  3  |  4  |  5  |
| :------------- | :-: | :-: | :-: | :-: | :-: |
| **Gyakoriság** |  4  |  2  |  1  |  1  |  2  |

### Relatív Gyakoriság
A **relatív gyakoriság** az adott érték gyakoriságának és az összes elem számának az hányadosa ($\frac{\text{gyakoriság}}{\text{elemek száma}}$).

| Érték | 1 | 2 | 3 | 4 | 5 |
| :--- | :-: | :-: | :-: | :-: | :-: |
| **Relatív gyakoriság** | $\frac{4}{10}$ | $\frac{2}{10}$ | $\frac{1}{10}$ | $\frac{1}{10}$ | $\frac{2}{10}$ |

---

## Módusz és Medián

### Módusz
A leggyakoribb elem az adatsokaságban.
- **Egymóduszú adatsokaság:** $1 \text{ db}$ módusz megadása.
- **Kétmóduszú adatsokaság:** $2 \text{ db}$ módusz megadása.
- **Többmóduszú adatsokaság:** nem adunk meg móduszt.

*A példában a leggyakoribb érték az $1$ (4 db van belőle), így a **módusz = 1**.*

### Medián
Az adatsokaság középső eleme, miután a mintát **növekvő sorrendbe** rendeztük.
- **Páratlan számú elemnél:** a pontosan középső elem.
- **Páros számú elemnél:** a két középső elem átlaga.

*A példában rendezve: $1, 1, 1, 1, 2, 2, 3, 4, 5, 5$ (10 elem, páros).*  
A két középső elem a 2 és a 2.
$$\text{Medián} = \frac{2 + 2}{2} = 2$$

---

## Terjedelem és Relatív Terjedelem

- **Terjedelem:** Véges elemű adatsokaság legnagyobb és legkisebb elemének különbsége.
  - Legnagyobb elem: $5$
  - Legkisebb elem: $1$
  - $\text{Terjedelem} = 5 - 1 = 4$

- **Relatív terjedelem:** 
  $$\text{Relatív terjedelem} = \frac{\text{terjedelem}}{\text{átlag}}$$
  *A példa adataival:* 
  $$\frac{4}{2{,}5} = 1{,}6$$

---

## Átlagtól Való Eltérés (Szóródási Mutatók)

Legyenek az elemek $x_1, x_2, x_3, \dots, x_n$, és az átlagük $\bar{X}$.

- **Átlagos abszolút eltérés:**
  $$\frac{|\bar{X} - x_1| + |\bar{X} - x_2| + |\bar{X} - x_3| + \dots + |\bar{X} - x_n|}{n}$$

- **Szórás ($\sigma$):**
  $$\sigma = \sqrt{\frac{(\bar{X} - x_1)^2 + (\bar{X} - x_2)^2 + (\bar{X} - x_3)^2 + \dots + (\bar{X} - x_n)^2}{n}}$$