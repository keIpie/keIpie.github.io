---
layout: post
title: Problemy kratowe
---

Znane problemy kratowe, na bazie których budowane są postkwantowe schematy kryptograficzne.

### Problem LWE

Niech $\mathbb{T} = \mathbb{R}/\mathbb{Z}$ oznacza odcinek [0,1), $\phi$ będzie rozkładem prawdopodobieństwa na $\mathbb{T}$.
Niech $s \in \mathbb{Z}_q^n$ będzie ustalonym wektorem. Niech

- $a$ pochodzi z rozkadu jednostajengeo na $\mathbb{Z}_q^n$,
- $e \in \mathbb{T}$ pochodzi z rozkłądu $\phi$,
- $t = a \cdot s /q + e$, gdzie dzielenie przez $q$ jest homomorfizmem $\mathbb{Z} \rightarrow \mathbb{T}$.

Problem LWE polega na znalezieniu $s$ mając dostęp do dowolnie wielu losowych par $(a,t) \in \mathbb{Z}_q^n \times \mathbb{T}$.

### Problem RLWE

Zauważmy, że chcąc użyć problemu LWE do szyfrowania, znajdziemy się w sytuacji, w której tajny $n$-elementowy wektor ukrywamy w jednej liczbie.
Przez to użycie problemu LWE do szyfrowanie nie jest efektywne. Złożoność zmieniejszy wykorzystanie struktury pierścienia i zastąpienie iloczynu
skalarnego, użytego do konstrukcji par $(a,t)$, mnożeniem w pierścieniu.

Niech $\varphi(x)$ będzie wielomianem nierozkładalnym nad $\mathbb{Z}[x]$. Niech $s(x)$ będzie ustalonym wielomianem z pierścienia $\mathbb{Z}_q[x]/\varphi(x)$
o małych współczynnikach. Niech

- $a_i(x)$ zbiór losowych wielomianów z $\mathbb{Z}_q[x]/\varphi(x)$,
- $e_i(x)$ zbiór losowych wielomianów z $\mathbb{Z}_q[x]/\varphi(x)$ o małych współczynnikach,
- $t_i(x) = a_i(x) \cdot s(x) + e_i(x)$.
