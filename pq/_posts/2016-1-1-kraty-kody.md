---
layout: post
title: Kraty, kody, q-kraty
---

kraty a kody liniowe - czym to się różni...

### kraty

kraty to $\mathbb{Z}$-moduły, czyli odpowiedniki przestrzeni liniowych nad pierścieniem $\mathbb{Z}$

### kody

kody liniowe to $k$-wymiarowe podprzestrzenie przestrzeni liniowych na ciałami skończonymi $\mathbb{Z}_q^n$.
takie kody nazywane są też kodami q-arnymi.

### odległości między elementami

w kodach odległość między słowami definiujemy jako odległość Hamminga, zliczającą liczbę pozycji, na których dwa słowa
kodowe mają różne wartości. minimalną odległością Hamminga kodu nazywamy najmniejszą liczbę pozycji na których różnią się
dwa słowa z zadanego kodu. tworząc kod korekcyjny chcemy, aby minimalna odległość była jak największa - wtedy możemy wykryć
i poprawić więcej błędów, które mogły pojawić się podczas transmisji wiadomości drogą radiową.

w kratach długość wektorów i odległość między wektorami obliczamy przy pomocy metryki euklidesowej.

### q-kraty

każdemu kodowi liniowemu można jednozacznie przyporządkować kratę. kodom będącym podprzestrzeniami $\mathbb{Z}_q^n$
odpowiadają tak zwane kraty q-arne, czyli kraty $L$, dla których $q\mathbb{Z}^n \subseteq L$. z warunku tego wynika, że
wektor $x \in \mathbb{Z}$ należy do q-arnej kraty $L_q$ wtedy i tylko wtedy, gdy $x \pmod{q}$ również należy do $L_q$.

w zastosowaniach kryptograficznych można myśleć, że krat q-arne do podgrupy $\mathbb{Z}_q^n$.

w odróżnieniu od kodów q-arnych, do q-arnych krat należą nie tylko wektory $x \pmod{q}$, ale też $x$. dzięki temu
możemy rozważać euklidesową odległość.

przykładowa krata q-arna o bazie $B \in \mathbb{Z}^{n \times m}$ ma postać:
$$ L_q(B) = \{ y \in \mathbb{Z}^m ~|~ y = B s \pmod{q}~~for~some~s \in \mathbb{Z}^n~\} = B \mathbb{Z}^n + q\mathbb{Z}^m$$

odpowiada ona kodowi liniowemu o macierzy generującej $B \in \mathbb{Z}_q^{n \times m}$

### kontrola parzystości

w teori kodowania ważną rolę odgrywają macierze kontroli parzystości. dzięki nim sprawdzamy, czy dane słowo należy do kodu.
można zdefiniowqać krótki ciąg dokładny:

$$ 0 \rightarrow \mathbb{Z}_q^k \stackrel{B}{\rightarrow} \mathbb{Z}_q^n \stackrel{H}{\rightarrow} \mathbb{Z}_q^{n-k} \rightarrow 0, $$

dla którego kolejnych przekształceń obraz wcześniejszego jest jądrem kolejnego. Słowa kodowe $C \subseteq \mathbb{Z}_q^n$ tworzą obraz
przy mnożeniu przez $B$ (powstały jako iloczyny wiadomości przez macierz generującą $B$) i są jądrem przy mnożeniu przez macierz kontroli
parzystości $H$ (iloczyn słowa kodowego i macierzy $H$ jest zerem wtedy i tylko wtedy kiedy słowo należy do kodu).

analogiczną rolę będą pełniły kraty kontroli parzystości, które można zdefiniować dla krat q-arnych (a odpowiadają macierzom
kontroli parzystości dla kodów):

$$ L_q^{\perp}(H) = \{ x \in \mathbb{Z}^m ~|~ H x = 0 \pmod{q} \}. $$

### kraty i kody dualne

każdemu elementowi $x \in \mathbb{R}^n$ możemy przyporządkować przekształcenie iloczynu skalarnego z $x$: $f_x(y)=x \cdot y$, będące homomorfizmem.
kratą dualną do kraty $L$ nazywamy kratę $L^*$, składającą się z homomorfizmów z kraty $L$ w zbiór liczb całkowitych z dodawaniem:

$$ L^* = Hom(L,\mathbb{Z}) = \{ x \in \mathbb{R}^n ~|~ x \cdot y \in \mathbb{Z} ~~~ \forall y \in L \}. $$

kodem dualnym nazywamy kod generowany przez macierz kontroli parzystości. można pokazać, że:

$$ C^* = \{ x \in \mathbb{Z}_q^n ~|~ x \cdot y = 0 ~~~ \forall y \in C \}.$$
