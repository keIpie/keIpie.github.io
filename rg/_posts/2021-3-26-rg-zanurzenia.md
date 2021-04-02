---
layout: post
title: Pierścienie grupowe a geometria
---

Jak wprowadzić geometrię w pierścieniach grupowych? Jak zdefiniować odległości.
Jakie zanurzenia zastosować.

Popularnie, zwłaszcza przy stosowaniu krat w kryptografii, stosuje się dwa typy zanurzeń, które
pozwalają zdefiniować pojęcie odległości: **zanurzenie kanoniczne** (cannonical embedding) oraz
**zanurzenie po współczynnikach** (coefficicent embedding).

###  normy przestrzeni wektorowych

Klasycznie normę definiujemy dla przestrzeni wektorowych $X$ nad ciałami $\mathbb{R}$ lub $\mathbb{C}$,
jako odwzorowanie tych przestrzeni w zbiór liczb rzeczywistych dodatnich:

$$ |\cdot|: X \rightarrow \mathbb{R}_+ $$

które dla dowolnych $x,y \in X$ oraz skalaru $\alpha$ spełnia trzy aksjomaty:

1. $x \geqslant 0$ oraz $\|x\| = 0 \rightarrow x=0$,

2. $\| \alpha \cdot x \| = | \alpha | \cdot \| x\|$,

3. $\|x+y\| \leqslant \|x\| + \| y \|$ (nierówność trójkąta).

### a co dla ciał skończonych?

Powyższej definicji nie możemy używać dla ciał skończonych, póki nie wiemy czym jest norma elementu ciała $| \alpha |$.
Aby wprowadzić normę na ciele skończonym najpierw określamy jego **waluację**, czyli funkcję,
która wprowadza miarę na elementach ciała. Niech $K$ będzie ciałem i niech $|\cdot|: K \rightarrow \mathbb{R}$.
Waluacja z definicji spełnia następujące własności:

1. $x \geqslant 0$ oraz $\|x\| = 0 \rightarrow x=0$,

2. $\|x+y\| \leqslant \|x\| + \| y \|$,

3. $\|x \cdot y\| = \|x\| \cdot \| y \|$.

Można pokazać, że zbiór niezerwoych wartości norm:

$$ | K | = \{ |x| ~|~ x \in K - \{0\} \}$$

jest multiplikatywną podgrupą $(0,\infty)$, nazywaną grupą waluacji. Ciała skończone mają trywialną grupę waluacji $|K|=\{1\}$,
ponieważ gdyby istniało $x$, takie że $\|x\| \neq 1$ to grupa $\{ \|x^n \| ~|~ n \in \mathbb{Z}\}$ byłaby nieskończona.

Na ciałach z zadaną waluacją (*valued fields*) możemy już wprowadzić normę zadaną w poprzednim paragrafie. Zauważmy, że
ponieważ ciała skończone mają trywialne waluacje to z warunku 2. definicji normy
$\| \alpha \cdot x \| = | \alpha | \cdot \| x\| = \|x\|$, co jest nieintuicyjne.

### a co dla $\mathbb{Z}$-modułów?

W kontekście krat i pierścieni interesują nas normy zadana dla modułów (a nie przesztrzeni wektorowych).

### zanurzenie kanoniczne

Zanurzenie kanoniczne stosowane jest przede wszystkim dla krat cyklotomicznych, ponieważ pozwala
mnożyć wektory poprzez mnożenie *po współrzędnych*. Zauważmy, że:

$$ \mathbb{Z}[x]/(x^n+1) \rightarrow \mathbb{C}[x]/(x^n+1) \rightarrow \bigoplus \mathbb{C}[x]/(x-e^{\frac{2\pi ik}{2n}}). $$

Podgrupa cykliczna generowana przez element $x$ w grupie multiplikatywnej $\mathbb{Z}[x]/(x^n+1)$:

$$ \langle x \rangle = \{x,x^2,\ldots x^{n-1},-1,-x,\ldots,-x^{n-1},1\} $$

ma rząd 2n. Jej poszczególne elementy możemy reprezentować poprzez zespolone pierwiastki z jedynki:

$$ p_k(x^j) = e^{\frac{2\pi ik \cdot j}{2n}}$$

Aby znaleźć zanurzenie kanoniczne dla pierścieni grupowych, można użyć nierozkładalnych reprezentacji
grup nieprzemiennych. Jednak jeśli reprezentacje mają wymiar większy niż 1, wtedy niemożliwe jest mnożenie
*po współrzędnych* i efektywniejsze może być stosowanie zanurzeń *po współczynnikach*.

### zanurzenie po współczynnikach

Pierścień grupowy $\mathbb{Z}[G]$ nad grupą $G$ rzędu $n$ jest izomorficzny z $\mathbb{Z}^n$. Elementy grupy
są zanurzane przy użyciu zaurzenia po współczynnikach (*coefficient embedding*) w $\mathbb{Z}^n$ przez
przekształcenie w wektory jednostkowe. Używając tego zanurzenia długość wektora $X$ obliczamy prz pomocy normy
Euklidesowej.

**Lemat 1** Niech $X,~Y \in R[G]$, wtedy norma ich iloczynu jest ograniczona z góry:

$$ \| XY \| \leqslant \sqrt{n} \| X \| \cdot \| Y \|. $$

**Dowód** Norma $l_{\infty}$ elementu $XY$ jest mniejsza od iloczynu $\|X\|\|Y\|$, co wynika
z [nierówności Cauchy'ego-Schwarza](https://pl.wikipedia.org/wiki/Nier%C3%B3wno%C5%9B%C4%87_Cauchy%E2%80%99ego-Schwarza).
