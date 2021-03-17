---
layout: post
title: Kraty, kody, q-kraty
---

kraty a kody liniowe - w czym są podobne, czym się różnią...

### kody

kody liniowe to $k$-wymiarowe podprzestrzenie przestrzeni liniowych na ciałami skończonymi $\mathbb{Z}_q^n$.
tego typu kody nazywane są też kodami q-arnymi. zadawane są przez *macierz generującą* $B \in \mathbb{Z}_q^{n \times k}$:

$$ C(B) = \{ Bx \in \mathbb{Z}_q^n ~|~ x \in \mathbb{Z}_q^k \}. $$

### kraty

kraty to $\mathbb{Z}$-moduły, czyli odpowiedniki przestrzeni liniowych nad pierścieniem $\mathbb{Z}$. ich elementy są całkowitoliczbowymi
kombinacjami $n$ liniowo niezależnych wektorów z $\mathbb{R}^n$ tworzących tak zwaną *bazę* kraty $B$:

$$ L(B) = \{ Bx \in \mathbb{Z}^n ~|~ x \in \mathbb{Z}^n \}. $$

### jeden kod/krata różne macierze/bazy

ta sama przestrzeń słów kodowych odpowiada wielu różnym kodom, które są zadane przez różne macierze generujące. kody które mają ten sam zbiór słów
kodowych nazywamy *równoważnymi*. zbiór słów kodowych jest ten sam, ale różny jest sposób w jaki przyporządkowujemy je wiadomościom, które możemy
permutować w dowolny sposób. dwa kody są równoważne, jeżeli ich macierze generujące $B,~B' \in \mathbb{Z}_q^{n \times k}$ są sobie równe z dokładnością do
przemnożenia przez macierz odwracalną wymiarów $k \times k$.

w kryptografii najczęściej rozważamy kraty pełnego wymiaru. ta sama krata ma wiele różnych baz. bazy $B, B' \in \mathbb{Z}^{n \times n}$ zadają tę samą kratę,
jeżeli jedną można przekształcić w druga przy pomocy mnożenia przez macierz unimodularną (odwracalną i o wyznaczniku $\pm 1$).

### odległości między elementami

w kodach odległość między słowami definiujemy jako odległość Hamminga, zliczającą liczbę pozycji, na których dwa słowa
kodowe mają różne wartości. minimalną odległością Hamminga kodu, oznaczaną symbolem $d$, nazywamy najmniejszą liczbę pozycji na których różnią się
dwa słowa z zadanego kodu. tworząc kod korekcyjny chcemy, aby minimalna odległość była jak największa - wtedy możemy wykryć
i poprawić więcej błędów, które mogły pojawić się podczas transmisji wiadomości drogą radiową. kod o minimalnej odległości d pozwoli
wykryć (d-1) błędów, a naprawić $\lfloor \frac{d-1}{2} \rfloor$ błędów.

w kratach długość wektorów i odległość między wektorami obliczamy przy pomocy metryki euklidesowej. minimalną odległość między
dwoma wektorami kraty zadaje najkrótszy wektor kraty, oznaczalny jako $\lambda_1$. dla krat dużych wymiarów znalezienie
najkrótszego wektora jest zadaniem obliczeniowo trudnym. najlepsze znane algorytmy (algorytm LLL, algorytm BKZ) wykonują uogólnioną
ortogonalizację wektorów bazowych w celu znalezienia najkróteszego wektora kraty (lub choćby wektora, którego długość jest bliska najkrótszej).

zauważmy, że odległość euklidesowa między słowami kodowymi o odległości Hamminga 1 może być dowolnie duża, a wektory kraty o bardzo małej odległości
euklidesowej mogą różnić się na *wszystkich pozycjach* (w wybranej bazie mieć wszystkie współczynniki różne).

### błędy

klasycznie kody były używane do korekcji błędów podczas transmisji. w kryptografii postkwantowej zarówno krat jak i kodów używa się
do szyfrowania wiadomości. zaszyfrowanie wiadomości polega na zakodowaniu jej w postaći pewnego słowa/wektora kodu/kraty, po czym dodania błędu,
którego nie można skorygować nie mając pewnej ważnej informacji, znanej tylko uprawnionemu użytkownikowi. po dodaniu błędu otrzymujemy szyfrogram,
który nie należy do kodu/kraty.

w systemach kodowych szyfrogram $c$ jest pewnym wektorem z przestrzeni $\mathbb{Z}_q^n$, nie należącym do podprzestrzeni kodu. skorygować błąd
może jedynie osoba posiadająca parametry kodu. usuwanie błędów i dekodowanie słów kodu, którego się nie zna jest problemem obliczeniowo trudnym. 

w systemach kratowych szyfrogram $c$ jest pewnym wektorem z przestrzni $\mathbb{R}^n$. do wektora kraty dodawany jest wektor błędu, o małej długości
w porównaniu z długością najkrótszego wektora kraty. nie znając krótkich wektorów kraty, obliczeniowo trudnym problemem jest znalezienie
wektora należącego do kraty, którego odległość euklidesowa od $c$ jest najmniejsza (problem *znalezienia najbliższego wektora*).

### q-kraty

każdemu kodowi liniowemu można jednozacznie przyporządkować kratę. kodom będącym podprzestrzeniami $\mathbb{Z}_q^n$
odpowiadają tak zwane kraty q-arne, czyli kraty $L$, dla których $q\mathbb{Z}^n \subseteq L$. z warunku tego wynika, że
wektor $x \in \mathbb{Z}$ należy do q-arnej kraty $L_q$ wtedy i tylko wtedy, gdy $x \pmod{q}$ również należy do $L_q$.

w zastosowaniach kryptograficznych można myśleć, że kraty q-arne do podgrupy $\mathbb{Z}_q^n$.

w odróżnieniu od kodów q-arnych, do q-arnych krat należą nie tylko wektory $x \pmod{q}$, ale też $x$. dzięki temu
możemy rozważać euklidesową odległość.

przykładowa krata q-arna o bazie $B \in \mathbb{Z}^{n \times m}$ ma postać:
$$ L_q(B) = \{ y \in \mathbb{Z}^m ~|~ y = B s \pmod{q}~~dla~pewnego~~s \in \mathbb{Z}^n~\} = B \mathbb{Z}^n + q\mathbb{Z}^m$$

odpowiada ona kodowi liniowemu o macierzy generującej $B \in \mathbb{Z}_q^{n \times m}$

### kontrola parzystości

w teorii kodowania ważną rolę odgrywają macierze kontroli parzystości. dzięki nim sprawdzamy, czy dane słowo należy do kodu.
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