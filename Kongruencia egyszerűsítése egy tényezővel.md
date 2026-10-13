Date: 2026-10-13
Tags: 

Ha egy kongruencia mindkét oldalát elosztjuk egy $c$ számmal, a modulust is el kell osztanunk $c$ és $m$ legnagyobb közös osztójával:

$$c a \equiv c b \pmod m \iff a \equiv b \pmod{\frac{m}{\text{Inko}(c, m)}}$$

Mivel
$$
ca - cb = km \\
c(a - b)= km
$$
Legyen $d = lnko(c, m)$, és $c = d·c′$, $m = d·m′$, 
ahol $lnko(c′, m′) = 1$. 
Ezt behelyettesítve:

$$d·c′·(a − b) = k·d·m′$$

Egyszerűsítés d-vel (ez az egész számok körében megengedett, mert d ≠ 0):

$$c′(a − b) = k·m′$$

Ebből $m′ \space | \space c′(a − b).$ 
Mivel $lnko(c′, m′) = 1$, az $m′$ nem oszthat $c′-t$, 
ezért az $(a − b)$ tényezőt kell osztania:

$m′ | (a − b)$, azaz $a − b = t·m′$ alkalmas $t$ egészre.

Ez azt jelenti, hogy

$$a ≡ b (mod \space m/d).$$

Megjegyzés: Ha $c$ és $m$ relatív prímek ($\text{Inko}(c, m) = 1$), akkor a modulus nem változik, vagyis egyszerűen eloszthatunk $c$-vel mindkét oldalon.


Related concepts:
[[Index - Diszkrét matematika]]
[[Kongruencia megoldhatóság feltétel]]
[[Kétismeretlenes diofantoszi egyenlet megoldhatósága]]

Source:
