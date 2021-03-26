---
layout: post
title: Pierścienie grupowe a geometria
---

Jak wprowadzić geometrię w pierścieniach grupowych? Jak zdefiniować odległości.
Jakie zanurzenia zastosować.

Popularnie, zwłaszcza przy stosowaniu krat w kryptografii, stosuje się dwa typy zanurzeń, które
pozwalają zdefiniować pojęcie odległości: zanurzenie kanoniczne, zanurzenie po współczynnikach.

Zanurzenie kanoniczne stosowane jest przede wszystkim dla krat cyklotomicznych, ponieważ pozwala
mnożyć wektory poprzez mnożenie *po współrzędnych*. Zauważmy, że:

$$ \mathbb{Z}[x]/(x^n+1) \rightarrow \mathbb{C}[x]/(x^n+1) \rightarrow \bigoplus \mathbb{C}[x]/(x-e^{\frac{2\pi ik}{2n}}). $$

Grupa cykliczna generowana przez element $\langle x \rangle = \{x,x^2,\ldots x^{n-1},-1,-x,\ldots,-x^{n-1},1\}$ ma rząd 2n.

Aby znaleźć zanurzenie kanoniczne dla pierścieni grupowych, można użyć nierozkładalnych reprezentacji
grup nieprzemiennych. Jednak jeżeli reprezentacje mają wymiar większy niż 1 niemożliwe jest mnożenie
*po współrzędnych* i efektywniejsze może być stosowanie zanurzeń *po współczynnikach*.
