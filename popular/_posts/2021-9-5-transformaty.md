---
layout: post
title: Szybkie obliczenia a transformaty
---

W jakich pierścieniach można szybko wykonywać obliczenia i jak to robić.

### Szybkie mnożenie wielomianów

Załóżmy, że chcemy wymnożyć dwa wielomiany o $n$ współczynnikach:

$$ a(x) = a_{n-1} x^{n-1} + a_{n-2} x^{n-2} + \ldots a_1 x + a_0, $$
$$ b(x) = b_{n-1} x^{n-1} + b_{n-2} x^{n-2} + \ldots b_1 x + b_0. $$

Wynikiem mnożenia jest wielomian $c(x)$ o $2n$ współczynnikach, zadanych wzorem:

$$ c_k(x) = \sum_{i+j=k} a_ib_j x^k. $$

Aby brutalnie obliczyć współczynniki wielomianu $c(x)$ musimy wykonać $O(n^2)$
($O(n)$ mnożeń aby obliczać każdy z $O(n)$ współczynników).

### Transformata DFT i algorytm Cooleya-Tukeya

### Transformata NTT

### Transformata Fouriera a teoria reprezentacji grup

### Reprezentacje grupy cyklicznej

### Szybkie mnożenie wielomianów w języku teorii reprezentacji
