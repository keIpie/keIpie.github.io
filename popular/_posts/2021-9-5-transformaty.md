---
layout: post
title: Szybkie obliczenia a transformaty
---

W jakich pierścieniach można szybko wykonywać obliczenia i jak to robić.

### Szybkie mnożenie wielomianów

Załóżmy, że chcemy wymnożyć dwa wielomiany stopnia $n$:

$$ a(x) = a_{n-1} x^{n-1} + a_{n-2} x^{n-2} + \ldots a_1 x + a_0, $$

$$ b(x) = b_{n-1} x^{n-1} + b_{n-2} x^{n-2} + \ldots b_1 x + b_0. $$

Wynikiem mnożenia jest wielomian $c(x)$ stopnia $2n$ o współczynnikach, zadanych wzorem:

$$ c_k(x) = \sum_{i+j=k} a_ib_j x^k. $$

Aby brutalnie obliczyć współczynniki wielomianu $c(x)$ musimy wykonać $O(n^2)$
($O(n)$ mnożeń aby obliczać każdy z $O(n)$ współczynników).

### Ewaluacja i interpolacja

Złożóność mnożenia wielomianów można zmniejszyć z kwadratowej $O(n^2)$ na liniowo-logarytmiczną
$O(n log n)$, stosując następującą metodę:

1. **Ewaluacja** Wybierz $2n+1$ różnych punktów $x_0,~x_1,~\ldots x_{2n}$ i oblicz wartosci
wielomianów $a$ i $b$ w tych punktach.

2. **Mnożenie** Wykonaj mnożenie wartości obu wielomianów w wybrancyh punktach:

$$ y_i = a(x_i) \cdot b(x_i) = c(x_i).$$

3. **Interpolacja** Interpoluj wielomian $c(x)$ na podstawie wartości jego $2n+1$ punktach:

$$ (x_0,~y_0),~(x_1,~y_1),~\ldots~(x_{2n}, y_{2n}). $$

Sama zaprezentowana wyżej metoda nie przynosi jeszcze korzyści - sama ewaluacja wielomianów
w $2n$ punktach ma złożoność kwadratową. Zmniejszenie złożoności przyniesie dopiero
odpowiedni wybór punktów $x_i$ oraz sprytna metoda wielopunktowej ewaluacji.

### Pierwiastki z jedynki i algorytm Cooleya-Tukeya

Aby efektywnie wykonać ewaluację wielomianu dokonajmy dwóch wyborów:

1. Niech $N = 2n = 2^q$ będzię potęgą dwójki.

2. Wybierzmy punkty $x_i = \omega^i$, gdzie $\omega$ jest $N$-tym pierwiastkiem pierwotnym z jedynki, to znaczy:
  $\omega^N = 1$ oraz dla każdego $k<N$ zachodzi $\omega^k \neq = 1$.

Ewaluację wielomianu $a(x)$ stopnia $N$ w punktach ${x_i}_i=0^{N-1}$ wykonujemy obliczając jego transformatę:

$$ T_{N,\omega}(a) = \sum_{j=0}&{N-1} a(w^j) x^j.$$

Zauważmy, że poszczególne współczynniki transformaty wielomainu stanowią wartości $a(x)$ w wybranych punktach.

### Transformata NTT

### Transformata Fouriera a teoria reprezentacji grup

### Reprezentacje grupy cyklicznej

### Szybkie mnożenie wielomianów w języku teorii reprezentacji
