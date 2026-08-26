
## 1. DIREKT BIZONYÍTÁS

* Igaz állításokból indulva helyes logikai lépések során a bizonyítandó állításhoz jutunk.
    * **Pl.:** Másodfokú megoldóképlet bizonyítása (algebrai úton, ekvivalens átalakításokat végezve), logaritmus azonosságai.

---

## 2. INDIREKT BIZONYÍTÁS

* Megmutatjuk, hogy állításunk tagadása/ellentettje egy lehetetlen állítás.
    * **Pl.:** Végtelen sok prímszám van.
    * **Tétel:** $\sqrt{2}$ irracionális.

### Példa bizonyítás: $\sqrt{2}$ irracionális

**Tfh.** $\sqrt{2}$ racionális $\longrightarrow \sqrt{2} = \frac{p}{q}$, ahol $p, q \in \mathbb{Z}$, $p$ és $q$ relatív prímek, valamint $q \neq 0$.

$$2 = \frac{p^2}{q^2}$$
$$\underbrace{2q^2}_{\text{páros}} = p^2 \implies p^2 \text{ páros}$$

Ha $p^2$ páros $\longrightarrow p = 2k \quad (k \in \mathbb{Z})$.

$$2q^2 = 4k^2$$
$$q^2 = 2k^2 \implies \underbrace{q^2}_{\text{páros}} \implies q \text{ is páros}$$

**Ellentmondás:** $p$ is és $q$ is páros, így nem lehetnek relatív prímek. Ezért $\sqrt{2}$ irracionális.

---

## 3. TELJES INDUKCIÓ

3 lépésre épül:

i) Megnézzük, hogy $n=1$-re igaz-e (lehet, hogy nem $n=1$-től igaz!).
ii) Feltesszük, hogy $n=k$-ra is igaz $\longrightarrow$ **INDUKCIÓS FELTÉTEL**.
iii) Ekkor belátjuk, hogy $n=k+1$-re is igaz.

---

### 1. Példa: Négyzetszámok összege

**Tétel:** 

$$1^2 + 2^2 + \dots + n^2 = \frac{n(n+1)(2n+1)}{6}$$

**Bizonyítás:**

1. **Bázislépés ($n=1$):**
   $$1^2 = \frac{1(1+1)(2\cdot 1+1)}{6}$$
   $$1 = \frac{6}{6} \implies n=1 \quad \checkmark$$

2. **Indukciós feltétel ($n=k$):**
   Feltesszük, hogy $n=k$-ra is igaz:
   $$1^2 + 2^2 + 3^2 + 4^2 + \dots + k^2 = \frac{k(k+1)(2k+1)}{6}$$

3. **Indukciós lépés ($n=k+1$):**
   Belátjuk, hogy $n=k+1$-re is igaz:
   $$\underbrace{1^2 + 2^2 + 3^2 + \dots + k^2}_{\text{Indukciós feltétel}} + (k+1)^2 = \frac{(k+1)(k+2)(2(k+1)+1)}{6}$$
   
   $$\frac{k(k+1)(2k+1)}{6} + (k+1)^2 = \frac{(k+1)(k+2)(2k+3)}{6}$$
   
   Kiemelünk $(k+1)$-et mindkét oldalon, majd átalakítunk:
   $$\frac{k(2k+1)}{6} + (k+1) = \frac{(k+2)(2k+3)}{6}$$
   $$\frac{2k^2 + k + 6k + 6}{6} = \frac{2k^2 + 3k + 4k + 6}{6}$$
   $$2k^2 + 7k + 6 = 2k^2 + 7k + 6 \quad \checkmark$$

---

### 2. Példa: Oszthatósági feladat

Minden $n$ esetén ($n \in \mathbb{N}$):

$$6 \mid n(2n+1)(7n+1)$$

**Bizonyítás:**

i) **Megnézem, hogy $n=0$-ra igaz-e:**
   $$6 \mid 0(2\cdot 0+1)(7\cdot 0+1)$$
   $$6 \mid 0 \quad \checkmark$$

ii) **Indukciós feltétel ($n=k$):**
   Feltesszük, hogy $n=k$-ra is igaz:
   $$6 \mid k(2k+1)(7k+1) = 14k^3 + 9k^2 + k$$

iii) **Indukciós lépés ($n=k+1$):**
   Belátjuk, hogy $n=k+1$-re is igaz:
   $$6 \mid (k+1)(2k+3)(7k+8)$$
   
   Kibontva a zárójeleket:
   $$(k+1)(2k+3)(7k+8) = (2k^2 + 5k + 3)(7k+8) = 14k^3 + 16k^2 + 35k^2 + 40k + 21k + 24$$
   $$= 14k^3 + 51k^2 + 61k + 24$$
   
   Átrendezve az indukciós feltétel alapján:
   $$\underbrace{(14k^3 + 9k^2 + k)}_{6\text{-al osztható}} + \underbrace{42k^2}_{6\text{-al osztható}} + \underbrace{60k}_{6\text{-al osztható}} + \underbrace{24}_{6\text{-al osztható}}$$
   
   Mivel minden tagja osztható 6-tal, az összeg is osztható 6-tal. $\quad \checkmark$

---

## 4. SKATULYA-ELV

* Ha van $n$ db skatulya és ezekbe legalább $n+1$ tárgyat helyezünk el, akkor lesz legalább egy skatulya, amibe több tárgy is kerül.
    * **Pl.:** Oszthatósági, maradékos feladatok, csoportosítási feladatok.

### Példa:
8 egész szám között biztosan van két olyan, amelyek különbsége osztható 7-tel.

* **Bizonyítás:** Egy egész szám 7-tel osztva $0, 1, 2, 3, 4, 5, 6$ (7-féle) maradékot adhat. 8 szám esetén a skatulya-elv alapján biztosan lesz két olyan szám, ami 7-tel osztva ugyanazt a maradékot adja. Ha őket egymásból kivonjuk, akkor a különbség biztosan 7-tel osztható.

---

## 5. VÉGTELEN LESZÁLLÁS

* Általában **diofantoszi egyenletek** (egész együtthatós egyenletek, melyekben általában több ismeretlen van, mint egyetlen, de a megoldásokat az egész vagy természetes számok között keressük) ellentmondásosságának bebizonyításához használjuk.
* Végtelen leszállás folyamán feltételezzük, hogy az egyenletnek van egy pozitív egész megoldása, bebizonyítjuk, hogy létezik egy ennél kisebb pozitív megoldása is, majd ezt folytatva végtelen sok egyre csökkenő pozitívak sorozatát kapjuk, ami nyilvánvalóan ellentmondás.

### Példa:
Bizonyítsuk be, hogy a $2q^2 = p^2$ egyenletnek nincs megoldása a pozitív egész számok halmazán! (**IGAZ**)

* **Bizonyítás:** Legyen $p$ és $q$ is pozitív egész megoldáspárjai az egyenletnek.

$$2q^2 = p^2$$
$$\underbrace{2q^2}_{\text{páros}} \implies p^2 \text{ páros} \implies p \text{ páros} \implies p = 2k \quad (k \in \mathbb{N}^+)$$

Behelyettesítve:
$$2q^2 = 4k^2$$
$$q^2 = 2k^2 \implies q^2 \text{ páros} \implies q \text{ páros} \implies q = 2n \quad (n \in \mathbb{N}^+)$$

Ezt beírva:
$$4n^2 = 2k^2$$
$$2n^2 = k^2 \implies k^2 \text{ páros} \implies k \text{ páros}$$

Ezt folytatva végtelen sok egyre csökkenő pozitív egész szám sorozatát kapnánk $\implies$ **Ellentmondás**.



---

## 6. LOGIKAI SZITA (SZITAFORMA)

Elszámolással járó bizonyításokban használjuk.

**Két halmaz esetén:**

$$|A \cup B| = |A| + |B| - |A \cap B|$$

**Három halmaz esetén:**

$$|A \cup B \cup C| = |A| + |B| + |C| - |A \cap B| - |A \cap C| - |B \cap C| + |A \cap B \cap C|$$

---

### Példa:

**Kérdés:** 100-nál kisebb pozitív egészek között hány 2-vel vagy 3-mal osztható van?

* $49 \text{ db } 2\text{-vel osztható} \implies |A| = 49 \text{ db}$
* $33 \text{ db } 3\text{-mal osztható} \implies |B| = 33 \text{ db}$
* $16 \text{ db } 6\text{-tal osztható} \implies |A \cap B| = 16 \text{ db}$

$$|A \cup B| = |A| + |B| - |A \cap B|$$
$$|A \cup B| = 49 + 33 - 16 = 66 \text{ db}$$

---

## 7. PÉLDAADÁS

* **"Van olyan..."** $\longrightarrow$ Kell hozni egyetlen jó példát $\longrightarrow$ **IGAZ**
  * **Konstruktív bizonyítás:** létrehozunk egy példát.
* **"Mindig...", "Minden...", "Sosem...", "Semelyik..."** $\longrightarrow$ Kell hozni egyetlen ellenpéldát $\longrightarrow$ **HAMIS**

---

## 8. FELÉPÍTŐ ÉS LEBONTÓ MÓDSZEREK

* **Felépítő:** Összeépítjük alesetekből.
* **Lebontó:** Elhagyjuk a nem megfelelő eseteket.

* **Pl.:** Esetszétválasztás, konstruktív és kizáró módszerek.