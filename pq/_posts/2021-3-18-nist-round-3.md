---
layout: post
title: NIST PQ - kandydaci na PKE - runda 3
---

Szyfry kandydującde na standard na postkwantowy schemat wymiany klucza (PKE),
które zostały zakwalifikowane do finałowej rundy 3 konkursu organizowanego przez NIST.
Do finału przeszedł jeden kandydat wykorzystujący problemy kodowe i trzech kandydatów
opartych na problemach w kratach teorio-liczbowych.

### [Classic McEliece](https://classic.mceliece.org/) - KODY

McEliece to kryptosystem oparty na liniowych binarnych kodach Goppy i trudności
problemu dokodowania w obecności odpowiednio wielu błędów.

Kody algebraiczno-geometryczne (AG-kody), nazywane też kodami Goppy, to ogólny typ kodów liniowych
konstruowanych przy użyciu krzywej algebraicznej $X$ nad ciałem skończonym $\mathbb{F}_q$. W kryptografii
często używane są binarne kody Goppy, które mają lepsze własności korekcyjne od kodów nad pozostałymi ciałami.

Idea systemu polega na wybraniu (n,k)-kodu o macierzy generującej $G$, który umożliwia korekcję $t$ błędów,
a następnie przedstawieniu go w zaszyfrowanej postaci $SGP$, jako pewien losowy $(n,k)$-kod korekcyjny.
Znając macierz $SGP$ można zakodować wiadomość i dodać błąd, zakłócający słowo kodowe na $t$ współrzędnych.
Jedynie osoba znająca prywatne macierze $S,P$ będzie w stanie skorygować błędy (umie wykorzystać własności kodu $G$).

### [CRYSTALS-KYBER](https://pq-crystals.org/) - KRATY

CRYSTALS używa kratowego problemu LWE w kratach modułowych (M-LWE). Kraty modułowe mają mniej struktury
algebraicznej niż kraty ideałowe (używane w problemie R-LWE), ale zachowują efektywnością większą od ogólnych
krat (z definicji problemu LWE).

Na kraty modułowe można patrzeć jak na kraty nie nad $\mathbb{Z}$, ale nad $R=\mathbb{Z}/P(x)$, dla pewnego
nierozkładalnego nad Q wielomianu $P(x)$ stopnia $d$. Ciałem, w którym będziemy chcieli badać normy i odległości
będize $K=\mathbb{Q}/P(x)$ (zamiast $\mathbb{Q}$). Rozważamy następujący moduł:

$$ M = \{ Bx~|~x \in R^k \}$$

gdze $B\in K^{k \times k}$ jest odwracalną macierzą, będącą odpowiednikiem bazy kraty. Aby badać normy wektorów
musimy dodać geometrię na tej strukturze algebraicznej. Do tego celu używamy zanurzenia kanonicznego. Niech
$\alpha_1,\ldots,\alpha_d$ będą zespolonymi pierwiastkami wielomianu $P(x)$. Zanurzeniem kanonicznym nazywamy przekształcenie:

$$ \sigma: K \rightarrow \mathbb{C}^d$$

$$ x \rightarrow (x(\alpha_1),\ldots,x(\alpha_d))$$

oraz zanurzenie:

$$ \sigma: K^k \rightarrow \mathbb{C}^{kd}$$

$$ (x_1,\ldots,x_k) \rightarrow (\sigma(x_1),\ldots,\sigma(x_k)).$$

Kratę modułową definiujemy formalnie jako:

$$ L(M) = \{ \sigma(x)~|~x \in M \} \subset \mathbb{C}^{kd}.$$

Tak zdefiniowana krata $L(M)$ jest klasyczną kratą nad $\mathbb{Z}$ o bazie: $(\sigma(b_1), \sigma(xb_1), \ldots, \sigma(x^{d-1}b_k))$.

W kryptografii rozważa się zazwyczaj kraty modułowe o wymiarach $k<10$ oraz $500\leqslant kd \leqslant 1500$.
Wybrana w KYBER struktura algebraiczna to pierścień: $R=\mathbb{Z}_{3329}[x]/(x^{256}+1)$ (d=256) and $k=2,3$ lub $4$ w zależności od wersji
algorytmu.

### [NTRU](https://ntru.org/) - KRATY

NTRU używa kratowego problemu NTRU w kratach cyklicznych. Więcej na temat [NTRU](https://keipie.github.io/ntru/).

### [SABER](https://www.esat.kuleuven.be/cosic/pqcrypto/saber/) - KRATY

SABER używa kratowego problemu M-LWR - module learning with rounding - uczenia w obecności zaokrągleń w kratach modułowych.
W często stosowanym problemie kratowym LWE - learning with errors - uczenia w obecności błędów. Problem LWE dotyczy niemożliwości
rozróżnienia rozkładów $(A,As+e)$ oraz $(A,b)$ dla losowych $a \in \mathbb{Z})q^n$ i $b \in \mathbb{Z}_q$ oraz błędu $e$ losowanego z
ustalonego rozkładu $\chi$.
Problem LWR zastepuje dodawanie małych losowych wartości z $\mathbb {Z}_q$ (błędów) deterministycznym zaokrąglaniem. Zaokrąglanie
$\lfloor \cdot \rfloor_p$ polega na stwierdzeniu do którego z $q/p$ przedziałów kolejnych liczb należy dana liczba.
Autorzy [pracy](https://eprint.iacr.org/2011/401.pdf) pokazali, że dla odpowiednio dużego stosunku $q/p$ i odpowiedniego rozkładu błędów
(w którym błędy są ponad-wielomianowo mniejsze stosunku) następujące rozkłady są nierozróżnialne:

$$ (A,\lfloor As \rfloor_p) \stackrel{stat.}{\approx} (A, \lfloor As + e\rfloor_p) \stackrel{comp.}{\approx} (A, \lfloor b \rfloor_p)$$

Druga aproksymacja wynika z trudności problemu LWE. Problemy M-LWR i M-LWE to odpowiedniki powyższych w kratach modułowych.
