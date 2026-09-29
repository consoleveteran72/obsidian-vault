Date: 2026-09-27
Tags: #definíció, #számelmélet, #oszthatóság

Angolul: Greatest common divisor (GCD)

## Definíció
 
 A $c$ egész számot az $a$ és $b$ egészek **közös osztójának** nevezzük, ha $c \mid a$ és $c \mid b$. A $c$ egész szám $a$ és $b$ **legnagyobb közös osztója**, ha közös osztójuk, valamint $a$ és $b$ minden $c'$ közös osztójára $c' \mid c$ teljesül.

## Példa 

(a) $2^7 - 1 \mid 2^{14} - 1, 2^{21} - 1$, 

(b) $3 \mid 123\,456, 123\,456\,789$.

# Legnagyobb közös osztó egyértelműsége 

## Állítás 

$a, b, c, c' \in \mathbb{Z}$ 
Ha $c$ és $c'$ is legnagyobb közös osztója (lnko-ja) az $a$ és $b$ számoknak, akkor: $$\vert c \vert = \vert c' \vert$$

> [!INFO] A legnagyobb közös osztó a számelméletben (előjeltől eltekintve) lényegében egyértelmű. Egy számpárnak két lnko-ja lehet: egy pozitív és egy negatív (pl. $12$ és $18$ lnko-ja a $6$ és a $-6$ is).

--- 
## Bizonyítás 

A bizonyítás a legnagyobb közös osztó definícióján alapul (miszerint az lnko-t a számok minden más közös osztója osztja).

* ***Induljunk ki abból,*** hogy $c$ és $c'$ is lnko-ja $a$-nak és $b$-nek. 

* Mivel $c$ lnko és $c'$ egy közös osztó $\implies c' \mid c$ 

* Mivel $c'$ lnko és $c$ egy közös osztó $\implies c \mid c'$ 
* Mivel a két egész szám kölcsönösen osztja egymást ($c' \mid c$ és $c \mid c'$), ezért a két szám legfeljebb az előjelében térhet el egymástól. Ebből következik, hogy abszolútértékük megegyezik: $$\vert c \vert = \vert c' \vert$$
---
## Megjegyzés 

Ha $c$ lnko-ja $a, b$-nek, akkor $-c$ is lnko-ja $a, b$-nek. $$d \mid a, b \implies d \mid c \iff d \mid -c$$



Related concepts:
[[Index - Diszkrét matematika#Oszthatóság]]

Source:


