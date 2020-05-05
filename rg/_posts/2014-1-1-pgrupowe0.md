---
layout: post
title: Pierścienie grupowe a kraty
---

Jak kraty się mają do pierścieni grupowych - przyjrzyjmy się podobieństwom. Przedstawimy definicje obu struktur,
a nastepnie przyjrzymy się problemom kratowym w kontekście pierścieni grupowych.

### Pierścień grupowy

Niech $G$ będzie grupą i $R$ pierścieniem. Pierścień grupowy $R[G]$ stanowi zbiór liniowych kombinacji

$$ \alpha = \sum_{g\in G} a_g g,$$

gdzie $g \in G$ oraz $a_g \in R$ i tylko skończenie wiele elementów $a_g$ jest niezerowych. Pierścień grupowy jest pierścieniem. Sumę elementów definiujemy jako

$$ \alpha + \beta = (\sum_{g\in G} a_g g) + (\sum_{g\in G} b_g g) = \sum_{g\in G} (a_g + b_g) g. $$

Iloczyn elementów definiujemy jako

$$ \alpha \cdot \beta = (\sum_{g\in G} a_g g) \cdot (\sum_{g\in G} b_g g) = \sum_{g,h\in G} a_g b_h gh.$$

### Krata teorio-liczbowa

Niech $B = \\{b_1,b_2,\ldots, b_n\\}$ będzie bazą wektorów zawartych w $\mathbb{R}^n$. Kratą $L$ nazywamy liniową kombinację wektorów bazy o współczynnikach całkowitych

$$ L = L(B) = \left\{ \sum_{i=1}^{n} a_ib_i~|~a_i \in \mathbb{Z} \right\}.$$

Elementy kraty przedstawiamy poprzez wektory współczynników $[a_1,a_2,\ldots,a_n]$ i nazywamy wektorami kraty.

### Pierścienie grupowe a kraty

Rozważmy kratę $L(B)$ i pierścień grupowy $\mathbb{Z}[G]$.

Kratę $L$ tworzą liniowe kombinacje wektorów z bazy $B$ o całkowitych współczynnikach.
Pierścień grupowy $\mathbb{Z}[G]$ tworzą liniowe kombinacje elementów grupy.
Tak więc obie struktury są $\mathbb{Z}$-modułami.

Różnica: Krata jest addytywną podgrupą $\mathbb{R}^n$ - możemy dodawać jej elementy, ale nie możemy mnożyć.
Pierścień grupowy jest pierścieniem - jego elementy możemy również mnożyć.

Aby móc wykonywać mnożenie na elementach kraty, rozważa się ideały krat.


### Ideał kraty

Niech $f \in \mathbb{Z}[x]$ będzie unormowanym wielomianem stopnia $n$. Pierścień ilorazowy $\mathbb{Z}[x]/f(x)$ potraktowany jako grupa adyytywna jest izomorficzny
z kratą $\mathbb{Z}^n$. Ideały pierścienia $I \subseteq \mathbb{Z}[x]/f(x)$ definiują odpowiadające im przy izomorfizmie podkraty $L(I) \subseteq \mathbb{Z}^n$.
<a href="https://en.wikipedia.org/wiki/Ideal_lattice" target="_blank">Ideałem kraty</a> nazywamy kratę $L(B)$ taką, że $B$ jest bazą przestrzeni złożonej z wektorów odpowiadających wielomianom $\\{ g \pmod{f} ~|~ g \in I \\}$ (**czy tak?**).

W ideałach krat definiujemy mnożenie wektorów poprzez mnożenie odpowiadających im wielomianów.

### Kraty cykliczne

Kraty cykliczne odpowiadają ideałom pierścienia $\mathbb{Z}[x]/(x^n-1)$. Pierścień ten jest izomorficzny z kratą $\mathbb{Z}^n$ poprzez izomorfizm $\mathbb{Z}$-modułów:

$$ i: \mathbb{Z}[x]/(x^n-1) \rightarrow \mathbb{Z}^n \\
g(x) = a_1 + a_2x + \ldots a_n x^{n-1} \stackrel{i}{\rightarrow} [a_1,a_2,\ldots,a_n].$$

Wynika stąd, że jeżeli pewien wektor należy do kraty cyklicznej to wszystkie jego cykliczne przesunięcia również. Weźmy dowolny wektor kraty cyklicznej, który odpowiada wielomianowi $g \in I \subseteq \mathbb{Z}[x]/(x^n-1)$

$$ [a_1,a_2,\ldots,a_n] \leftrightarrow g(x) = a_1+a_2x + \ldots a_n x^{n-1}.$$

Ponieważ $g(x) \in I$, to również $x \cdot g(x) \in I$. Zauważmy, że współczynniki $x \cdot g(x)$ są cyklicznie przesunięte względem współczynników $g(x)$

$$ x \cdot g(x) = x \cdot (a_1+a_2x + \ldots a_n x^{n-1}) = a_n + a_1x+a_2x^2 + \ldots a_{n-1} x^{n-1} \in I. $$

Stąd przesunięty wektor $[a_n,a_1,\ldots,a_{n-1}]$ również musi należeć do kraty cyklicznej.

Uogólniając powyższe rozumowanie możemy definiujemy mnożenie wektorów kraty poprzez mnożenie odpowiadających im wielomianów.


### Kraty cyklotomiczne

Kraty cyklotomiczne odpowiadają ideałom pierścienia $R = \mathbb{Z}[x]/(x^n+1)$ (nazwa od użytych do rozszerzenia wielomianów cyklotomicznych).

### Pierścienie grupowe a ideały krat

Niech  $B=\\{b_0,b_1,\ldots , b_{n-1}\\}$ jest bazą przestrzeni $\\{ g \pmod{f} \mid g \in I\\}$ dla pewnego ideału $I \in \mathbb{Z}[x]/f(x)$. Krata $L(B)$ jest posatci

$$ L(B) = \left\{ \sum_{i=0}^{n-1} a_ib_i~|~a_i \in \mathbb{Z} \right\}.$$

Pytanie 1: czy $L(B)$ jest ideałem pierścienia grupowego $\mathbb{Z}[G]$ dla pewnej grupy $G$?

#### Przykład 1:

Weźmy ideał będący całym pierścieniem $I=R$ oraz bazę $B = \\{ 1,x,\ldots, x^{n-1}\\}$.

$$ L(B) = \left\{ \sum_{i=0}^{n-1} a_ix^i~|~a_i \in \mathbb{Z} \right\}.$$

Weźmy $n$-elementową grupę cykliczną $G$ wtedy

$$ \mathbb{Z}[G] = \left\{ \sum_{i=0}^{n-1} a_ig^i~|~a_i \in \mathbb{Z} \right\}.$$

Ideał kraty $L(B)$ jest izomorficzny z pierścieniem grupowym $\mathbb{Z}[G]$ przez izomorfizm $x \rightarrow g$.

#### Przykład 2:

Niech $n=2k$. Weźmy ideał $I \subseteq R$ oraz bazę $B = \\{ 1,x^2,x^4\ldots, x^{2(k-1)}\\}$.

$$ L(B) = \left\{ \sum_{i=0}^{k-1} a_ix^{2i}~|~a_i \in \mathbb{Z} \right\}.$$

Weźmy $n$-elementową grupę cykliczną i rozważmy ideał pierścienia grupowego

$$ IG = \left\{ \sum_{i=0}^{k-1} a_ig^{2i}~|~a_i \in \mathbb{Z} \right\} \subseteq \mathbb{Z}[G].$$

Ideał kraty $L(B)$ jest izomorficzny z ideałem pierścieniem grupowego $IG$ przez izomorfizm $x^2 \rightarrow g^2$.

#### Przykład 3:

Weźmy ideał $I \subseteq R$ oraz bazę $B = \\{ b_1(x),b_2(x), \ldots, b_n(x)\\}$. Jak znaleźć grupę odpowiadającą bazie?

### Co dalej

Pierścienie grupowe to bardzo ogólna struktura. Ideały kart mogą być ideałami pierścieni grupowych.

Jak przeformułować problemy kratowe na język pierścieni grupowych?

A później jak przeformułować krypotosystemy oparte na problemach kratowych na język pierścieni grupowych?

Co się stanie jak zamiast pierścienia $\mathbb{Z}$ weżmiemy jakiś inny pierścień? Np nieprzemienny?

Co gdybyśmy wzięli pierścień macierzy? Tu na pewno pojawią się problemy z jednoznacznością rozkładu...
W liczbach całkowitych wiemy co to jest liniowa niezależność, a jak to mogłoby wyglądać dla macierzy?

Czym by wtedy była "dziedzina podstawowa" czyli dla krat równoległościan rozpięty przez wektory bazowe?
