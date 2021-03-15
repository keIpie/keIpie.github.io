---
layout: post
title: Macierze a szyfrowanie
---

jak i po co szyfrować macierze.

klaszyczna kryptografia zajmuje się szyfrowaniem wiadomości.
do tego celu zazwyczaj używa algebry przemiennej, teorii liczb i rachunku prawdopodobieństwa,
formułując obliczeniowo trudne problemy, na których opiera się bezpieczeństwo kryptosystemów.
wiadomości są kodowane w wybranych strukturach algebraicznych, a następnie szyfrowane poprzez
zanurzenie w większej strukturze, której pełne przeszukania jest niemożliwe, a szyfrogramy są
statystycznie nieodróżnialne od elementów losowych.

szyfrowanie macierzy pojawia się naturalnie w momencie, w którym chcemy zacząć szyfrować nie wiadomości
a funkcje. macierze odpowiadają funkcjom liniowym. przekształcenia nieliniowe da się zlinearyzować i zapisać
w postaci iloczynu macierzy (choć często bardzo wielu).

### jak szyfrować macierze nad ciałem

Ishai i Kushilevitz w pracy "Private Simultaneous Message Protocols with Applications" zdefiniowali następujący lemat.

**lemat**

niech $A$ i $A'$ będą macierzami nad ciałem skończonym $GF(q)$ tego samego rzędu $r$. istnieją odwracalne macierze
$R$ i $P$, które spełaniają:

$$ A' = R \cdot A \cdot P. $$  

**dowód**

z powyższegto lematu wynika, że rozkład $R \cdot A \cdot P$ jest nieodróznialny od losowego.

**lemat 2**

rozkład $R \cdot A \cdot P$, gdzie $R$ i $P$ są jednostajnie losowymi, niezależnymi macierzami odwracalnymi
zależy jedynie od rzedu macierzy $A$.

**dowód**

### jak szyfrować macierze nad pierścieniem

nad pierścieniem jest trudniej, ponieważ nie możemy zdefiniować rzędu macierzy.
