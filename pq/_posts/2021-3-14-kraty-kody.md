---
layout: post
title: Kraty, kody, q-kraty
---

działają w podobnych (a czasem identycznych) strukturach algebraicznych, ale różnią się zadaną **geometrią**.
postkwantowe systemy kryptograficzne oparte na kratach/kodach wykorzystują wyjście poza ich strukturę poprzez dodawanie **małych błędów**,
możliwych do skorygowania przez kogoś kto ma pełne dane o strukturze. żeby określić co to znaczy **mały** trzeba zdefiniować metrykę,
odległość między elementami struktury. kody i kraty robią to na różne sposoby. wynika stąd różnica w algorytmach dekodowania i ich
trudności. warto się nimi zajmować, bo w [konkursie na standard postkwantowego algorytmu wymiany klucza](https://keipie.github.io/nist-round-3/)
wszytskie finałowe rozwiązania wykorzystują albo kraty albo kody.

### kody

kody liniowe to $k$-wymiarowe podprzestrzenie przestrzeni liniowych na ciałami skończonymi $\mathbb{Z}_q^n$.
tego typu kody nazywane są też kodami q-arnymi. zadawane są przez *macierz generującą* $B \in \mathbb{Z}_q^{n \times k}$:

$$ C(B) = \{ Bx \in \mathbb{Z}_q^n ~|~ x \in \mathbb{Z}_q^k \}. $$

zawsze $k<n$, co oznacza, że przestrzeń wiadomości jest mniejsza od przestrzeni słów kodowych - ta nadmiarowość pozwala
na korekcję błędów.

### kraty

kraty to $\mathbb{Z}$-moduły, czyli odpowiedniki przestrzeni liniowych nad pierścieniem $\mathbb{Z}$. ich elementy są całkowitoliczbowymi
kombinacjami $k$ liniowo niezależnych wektorów z $\mathbb{R}^n$ tworzących tak zwaną *bazę* kraty $B \in \mathbb{Z}^{k \times n}$:

$$ L(B) = \{ Bx \in \mathbb{Z}^n ~|~ x \in \mathbb{Z}^k \}. $$

często rozważa sie kraty pełnych wymiarów, dla których $k=n$.

### jeden kod/krata, różne macierze/bazy

ta sama przestrzeń słów kodowych odpowiada wielu różnym kodom, które są zadane przez różne macierze generujące. kody które mają ten sam zbiór słów
kodowych nazywamy *równoważnymi*. zbiór słów kodowych jest ten sam, ale różny jest sposób w jaki przyporządkowujemy je wiadomościom, które możemy
permutować w dowolny sposób. dwa kody są równoważne, jeżeli ich macierze generujące $B,~B' \in \mathbb{Z}_q^{n \times k}$ są sobie równe z dokładnością do
przemnożenia przez macierz odwracalną wymiarów $k \times k$.

ta sama krata ma wiele różnych baz. bazy $B, B' \in \mathbb{Z}^{n \times n}$ zadają tę samą kratę, jeżeli jedną można przekształcić w druga przy
pomocy mnożenia przez macierz unimodularną (odwracalną i o wyznaczniku $\pm 1$). przemnożenie przez macierz unimodularną odpowiada wybraniu nowej
baz kraty, składającej się z kombinacji liniowej wektorów starej bazy. macierz ma wyznacznik $\pm 1$, ponieważ nie możemy skalować wektorów bazy
(takie przekształcenie nie jest odwracalne ze względu na nieodwracalność liczb całkowitych).

### odległości między elementami

w kodach odległość między słowami definiujemy jako odległość Hamminga, zliczającą liczbę pozycji, na których dwa słowa
kodowe (rzadziej: ich binarne reprezentacje) mają różne wartości.
minimalną odległością Hamminga kodu, oznaczaną symbolem $d$, nazywamy najmniejszą liczbę pozycji, na których różnią się
dwa słowa z zadanego kodu. ponieważ słowo zerowe zawsze należy do kodu, $d$ określa również najmniejszą możliwą liczbę niezerowych współczynników słowa.
tworząc kod korekcyjny chcemy, aby minimalna odległość była jak największa - wtedy możemy wykryć i poprawić więcej błędów,
które mogły pojawić się podczas transmisji wiadomości drogą radiową. kod o minimalnej odległości $d$ pozwoli
wykryć $(d-1)$ błędów, a naprawić $\lfloor \frac{d-1}{2} \rfloor$ błędów. wybór odległości Hamminga jako metryki, wydaje się naturalny
jeżeli weźmie się pod uwagę, że drogą radiową wysyłane były ciągi bitów. w konsekwencji były tylko dwie mozliwe wartości współczynników: 0 albo 1,
które mogły być różne na jeden tylko sposób (jak nie 0 to 1).

w kratach długość wektorów i odległość między wektorami obliczamy przy pomocy metryki euklidesowej. minimalną odległość między
dwoma wektorami kraty zadaje najkrótszy wektor kraty, oznaczany jako $\lambda_1$. dla krat dużych wymiarów znalezienie
najkrótszego wektora jest zadaniem obliczeniowo trudnym. najlepsze znane algorytmy (algorytm LLL, algorytm BKZ) wykonują uogólnioną
ortogonalizację wektorów bazowych w celu znalezienia najkróteszego wektora kraty (lub choćby wektora, którego długość jest bliska najkrótszej).

zauważmy, że odległość euklidesowa między słowami kodowymi o odległości Hamminga 1 może być dowolnie duża, a wektory kraty o bardzo małej odległości
euklidesowej mogą różnić się na *wszystkich pozycjach* (w wybranej bazie mieć wszystkie współczynniki różne).

dobór metryki nie jest przypadkowy. wprowadzenie metryki euklidesowej w kodach nie jest możliwe ze względu na ich modularność.
aby wprowadzić normę na przestrzeni liniowej nad ciałem skończonym, najpierw należy określić miarę elemnetów ciała - jego
[waluację](https://keipie.github.io/rg-zanurzenia/). W podlinkowanym artykule można przeczytać czemu ciała skończone muszą mieć
trywialną waluację i jak wpływa to na normę przestrzeni nad nimi.

### błędy

klasycznie kody były używane do korekcji błędów podczas transmisji. w kryptografii postkwantowej zarówno krat jak i kodów używa się
do szyfrowania wiadomości. zaszyfrowanie wiadomości polega na zakodowaniu jej w postaci pewnego słowa/wektora kodu/kraty, po czym dodaniu błędu,
którego nie można skorygować nie mając pewnej ważnej informacji, znanej tylko uprawnionemu użytkownikowi. po dodaniu błędu otrzymujemy szyfrogram,
który nie należy do kodu/kraty.

w systemach kodowych szyfrogram $c$ jest pewnym wektorem z przestrzeni $\mathbb{Z}_q^n$, nie należącym do podprzestrzeni kodu. skorygować błąd
(jeżeli jest dostatecznie mały) może jedynie osoba posiadająca parametry kodu. usuwanie błędów i dekodowanie słów kodu, którego się nie zna jest
problemem obliczeniowo trudnym.

w systemach kratowych szyfrogram $c$ jest pewnym wektorem z przestrzni $\mathbb{Z}^n$. do wektora kraty dodawany jest wektor błędu, o małej długości
w porównaniu z długością najkrótszego wektora kraty. nie znając krótkich wektorów kraty, obliczeniowo trudnym problemem jest znalezienie
wektora należącego do kraty, którego odległość euklidesowa od $c$ jest najmniejsza (problem *znalezienia najbliższego wektora*).

### q-kraty

każdemu kodowi liniowemu można jednozacznie przyporządkować kratę. kodom będącym podprzestrzeniami $\mathbb{Z}_q^n$
odpowiadają tak zwane kraty q-arne, czyli kraty $L$, dla których $q\mathbb{Z}^n \subseteq L$. z warunku tego wynika, że
wektor $x \in \mathbb{Z}$ należy do q-arnej kraty $L_q$ wtedy i tylko wtedy, gdy $x \pmod{q}$ również należy do $L_q$.

w zastosowaniach kryptograficznych kraty q-arne traktowane są jak podgrupy $\mathbb{Z}_q^n$ (którymi jednak nie są). w odróżnieniu
od kodów q-arnych, do q-arnych krat należą nie tylko wektory $x \pmod{q}$, ale też $x$. dzięki temu możemy rozważać euklidesową odległość.

przykładowa krata q-arna o bazie $B \in \mathbb{Z}^{n \times m}$ ma postać:

$$ L_q(B) = \{ y \in \mathbb{Z}^m ~|~ y = B s \pmod{q}~~dla~pewnego~~s \in \mathbb{Z}^n~\} = B \mathbb{Z}^n + q\mathbb{Z}^m$$

odpowiada ona kodowi liniowemu o macierzy generującej $B \in \mathbb{Z}_q^{n \times m}$

### kontrola parzystości

w teorii kodowania ważną rolę odgrywają macierze kontroli parzystości. dzięki nim sprawdzamy, czy dane słowo należy do kodu.
można zdefiniowqać krótki ciąg dokładny:

$$ 0 \rightarrow \mathbb{Z}_q^k \stackrel{B}{\rightarrow} \mathbb{Z}_q^n \stackrel{H}{\rightarrow} \mathbb{Z}_q^{n-k} \rightarrow 0, $$

dla którego kolejnych przekształceń obraz wcześniejszego jest jądrem kolejnego. Słowa kodowe $C \subseteq \mathbb{Z}_q^n$ tworzą obraz
przy mnożeniu przez $B$ (powstały jako iloczyny wiadomości przez macierz generującą $B$) i są jądrem przy mnożeniu przez macierz kontroli
parzystości $H$ (iloczyn słowa kodowego i macierzy $H$ jest zerem wtedy i tylko wtedy gdy słowo należy do kodu).

analogiczną rolę będą pełniły kraty kontroli parzystości, które można zdefiniować dla krat q-arnych (a odpowiadają macierzom
kontroli parzystości dla kodów):

$$ L_q^{\perp}(H) = \{ x \in \mathbb{Z}^m ~|~ H x = 0 \pmod{q} \}. $$

### kraty i kody dualne

każdemu elementowi $x \in \mathbb{R}^n$ możemy przyporządkować przekształcenie iloczynu skalarnego z $x$: $f_x(y)=x \cdot y$, będące homomorfizmem.
kratą dualną do kraty $L$ nazywamy kratę $L^*$, składającą się z homomorfizmów z kraty $L$ w zbiór liczb całkowitych z dodawaniem:

$$ L^* = Hom(L,\mathbb{Z}) = \{ x \in \mathbb{R}^n ~|~ x \cdot y \in \mathbb{Z} ~~~ \forall y \in L \}. $$

kodem dualnym nazywamy kod generowany przez macierz kontroli parzystości. można pokazać, że:

$$ C^* = \{ x \in \mathbb{Z}_q^n ~|~ x \cdot y = 0 ~~~ \forall y \in C \}.$$

### kraty i kody cykliczne

kraty/kody nazywamy cyklicznymi jeżeli gdy wektor/słowo o ustalonych współczynnikach $(c_1,c_2,\ldots,c_n)$
należy do kraty/kodu, to jego cykliczna rotacja $(c_n,c_1\ldots, c_{n-1})$ również.

jeżeli wektorom/słowom krat/kodów przyporządkujemy wielomiany o współczynnikach zadanych przez ich współrzędne, to rotacja cykliczna
słowa odpowiada mnożeniu wielomianu przez element $x$ modulo wielomian cykliczny $(x^n-1)$.
zarówno kraty jak i kody cykliczne odpowiadają ideałom w pierścienieach ilorazowych. kody cykliczne odpowiadają ideałom w pierścieniu
ilorazowym:

$$ R_C = \mathbb{Z}_q[x]/(x^n-1).$$

kraty cykliczne odpowiadają ideałom w pierścieniu ilorazowym:

$$R_L = \mathbb{Z}[x] / (x^n-1).$$

zauważmy od razu, że pierścień $R_C$ jest zarazem ideałem w pierścieniu ilorazowym $R_L$ generowanym przez liczbę pierwszą $q$.

pierścień **$\mathbb{Z}_q[x]$ jest dziedziną ideałów głównych** (*principal ideal domain*), stąd każdy kod $C$ odpowiada pewnemu ideałowi głównemu.
wynika stąd, że dla każdego kodu istnieje element $g$, generujący wszystkie pozostałe słowa kodowe. dodatkowo element $g$ musi być dzielnikiem
wielomianu $(x^n-1)$. jeżeli stopień wielomianu generującego $g$ wynosi $d$, to generuje on kod wymiaru $n-d$. kodem nierozkładalnym nazywamy
kod, który odpowiada nierozkładalnemu ideałowi (który z kolei powstał przy użyciu nierozkładalnego wielomianu).

pierścień **$\mathbb{Z}[x]$ nie jest dziedziną ideałów głównych** (bo $\mathbb{Z}$ nie jest ciałem i ma elementy nieodwracalne np. $2$, w konsekwencji ma ideały
które nie są główne np. $\langle 2,x \rangle$). stąd nie mówimy o generatorach krat cyklicznych. ich baza ma jednak szczególną konstrukcję.
załóżmy, że krata $L(B)$ odpowiada ideałowi $I \subseteq R_L$ wtedy:

$$ B = \{ g \pmod{x^n-1} ~|~ g \in I \}.$$

ciekawostka: niektóre nowe schematy kodowe, używają kodów quasi-cyklicznych, w których jeżeli słowo odpowiadające wielomianowi $c(x)$
należy do kodu, to również musi należeć słowo odpowiadające wielomianowi $x^b \cdot c(x) \pmod{x^n-1}$. dla $b=1$ mamy dokładnie kod cykliczny.

### kraty/kody ideałowe

kraty/kody cykliczne są szczególnym przypadkiem krat/kodów ideałowych, odpowiadających ideałom w pierścieniach $\mathbb{Z}[x]/f(x)$ oraz
$\mathbb{Z}_q[x]/f(x)$ dla wybranych wielomianów $f(x)$. z definicji na kraty i kody można patrzeć jak na grupy addytywne.
dzięki dodatkowej strukturze ideału, umożliwiamy mnożenie elementów należących do kraty/kody przez siebie (wcześniej mogliśmy tylko przez skalary).
pozwala to konstruować zaawansowane systemy kryptograficzne, pozwalające wykonywać działania na zaszyfrowanych elementach.

### dekodowanie - usuwanie błędów

popularnie dekodowaniem nazywa się metody wyznaczania zakłóconych błędem słów kodowych - z nich już łatwo odzyskać wiadomość.
generalnie szukamy słów kodowych, które różnią się od odebranego (zaszumionego) słowa na jak najmniejszej liczbie współrzędnych (odległość Hamminga).
dekodować można za pomocą technik algebraicznych i niealgebraicznych.
metody algebraiczne polegają na rozwiązywaniu układów równań, w których niewiadomymi jest umiejscowienie i wartości błędów.
niealgebraiczne metody próbują wykryć wzór błędu wykorzystując strukturalne własności kodu. najważniejsze niealgebraiczne
algorytmy to dekodowanie Meggitta (dla kodów cyklicznych), dekodowanie progowe Masseya oraz tzw. information set decoding.

analogiczne dekodowanie krat polega na szukaniu wektorów należących do kraty, leżących *najbliżej* zakłóconego wektora kraty,
przy czym tu *bliskość* opisywana jest przy pomocy metryki euklidesowej. popularnym algorytmem szukania najbliższego wektora kraty
jest algorytm Babaia, który zwraca dobry wynik pod warunkiem, że znane są krótkie wektory należące do kraty.
