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

aby określić statystyczne własności iloczynów macierzy Ishai i Kushilevitz dowiedzą następujące lematy [1].

**lemat 1**
niech $A$ i $A'$ będą macierzami nad ciałem skończonym $GF(q)$ tego samego rzędu $r$. istnieją odwracalne macierze
$R$ i $P$, które spełaniają:

$$ A = R \cdot A' \cdot P. $$  

**dowód**
za pomocą elementarnych operacji można sprowadzić $A'$ do postaci blokowej:

$$ C = \begin{bmatrix} I_r & 0 \\ 0 & 0 \end{bmatrix}. $$

elementarne operacje są liniowe i można je zapisać w postaci odwracalnych macierzy $R_1$ i $P_1$ spełniających:

$$ C = R_1 A' P_1. $$

analogicznie do postaci $C$ można sprowadzić macierz $A$, która jest tego samego rzędu $r$. Istnieją zatem
odwracalne maciere $R_2$ i $P_2$, spełniające:

$$ C = R_2 A P_2. $$

przyrównując otrzymane równania otrzymujemy tezę dla macierzy $R = R_2^{-1}R_1$ oraz $P=P_1 P_2^{-1}$.

z powyższegto lematu wynika, że rozkład $R \cdot A \cdot P$ jest nieodróznialny od losowego.

**lemat 2** rozkład $R \cdot A \cdot P$, gdzie $R$ i $P$ są jednostajnie losowymi, niezależnymi macierzami odwracalnymi
zależy jedynie od rzedu macierzy $A$.

**dowód** niech A i A' bedę ustalonymi macierzami tego samego rzędu $r$. Dla każdej macierzy $Q$ zdefiniujmy dwa rozkłady:

$$ S_Q = \{ (R,P) | RAP = Q \}, $$

$$ S_Q' = \{ (R',P') | R'A'P' = Q \}. $$

z lematu 1 wynika, że istnieją pewne macierze $R_0$ i $P_0$ takie, że $A = R_0 A' P_0$. stąd

$$ RAP = R(R_0 A' P_0)P = (R R_0) A' (P_0 P).$$

przekształcenie $(R,P) \rightarrow (R R_0, P_0 P)$ jest różnowartościowe z $S_Q$ w $S_Q'$, podobnie przekształcenie odwrotne
$(R',P') \rightarrow (R' R_0^{-1}, P_0^{-1} P')$ jest różnowartościowe z $S_Q'$ w $S_Q$. w konsekwencji $|S_Q| = |S_Q'|$.
ponieważ każda para $(R,P)$ wybierana jest z takim samym prawdopodobieństwem, rozkłady RAP i RA'P są jednakowe.

Ishai i Kushilevitz analizowali też serię eksperymentów, gdzie poza szyfrowaniem macierzy przez wymnażanie z dwóch stron
przez macierze odwracalne do iloczynu dodaje się też mały błąd. analizowany protokół polegał na dodaniu zaszyfrowanych macierzy,
a błędy były tak dobrane, żeby sumowały się do zera. autorzy udawadniają dobre statystyczne własności szyfrowania.

### jak szyfrować macierze nad pierścieniem

nad pierścieniem jest trudniej, ponieważ nie możemy zdefiniować rzędu macierzy.

### literatura

[1] "Private Simultaneous Message Protocols with Applications" - Ishai, Kushilevitz
