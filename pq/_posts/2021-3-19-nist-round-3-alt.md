---
layout: post
title: NIST PQ - alternatywni PKE - runda 3
---

Poza podstawowymi kandydatami, wciąż brane są pod uwagę rozwiązania alternatywne, które
w inny sposób definiują bezpieczeństwo. Mają być użyte w razie złamania lub odkrycia
ataków ograniczających bezpieczeństwo lub efektywność podstawowych kandydatów.

### [BIKE](http://bikesuite.org/) - KODY

Algorytm wykorzystuje kody QC-MDPC (Quasi-Cyclic Moderate Density Parity-Check).

### [HQC](http://pqc-hqc.org) - KODY

HQC (Hamming Quasi-Cyclic) działa w kodach quasi-cyklicznych.

### [FrodoKEM](http://frodokem.org) - KRATY

Bezpieczeństwo algorytmu opiera się na problemie LWE w nieustrukturyzowanych kratach.
Frodo przeszedł jako kandydat alternatywny, ponieważ jego efektywność jest mniejsza od
efketywności rozwiązań w kratach modularnych (jak pozostali kandydaci), ale gdyby powstały
ataki na kraty z dodatkową strukturą - będziemy mieli przebadaną bezpieczną wersję.

### [NTRU Prime](https://ntruprime.cr.yp.to/) - KRATY

NTRU Prime to alternatywa dla klasycznego NTRU (zdefiniowanego w kratach cyklicznych)
oraz NTRU NTT (zdefiniowanego w kratach cyklotomicznych). W tym przypadku konstruowana
struktura algebraiczna jest izomorficzna z rozszerzonym ciałem skończonym (wielomian używany
do konstrukcji ilorazowego pierścienia wielomianów jest nierozkładalny nad ciałem współczynników).
Bezpieczeństwo NTRU Prime opiera się na wielokości grup Galois skonstruowanego rozszerzenia.
Autorzy zachwalają go, jako nieustrukturyzowaną wersję schematów opartych na problemie NTRU.
Ze względu na alternatywną definicję bezpieczeństwa, która eliminuje niektóre ataki algebraiczne,
schemat przeszedł do 3 rundy jako kandydat alternatywny.

### [SIKE](http://sike.org/) - IZOGENIE

Algorytm do wymiany klucza używa pseudo-losowych ścieżek przez grafy supersingualrnych izogenii.
Tego typu grafy są ekspendarami, czyli mają mało krawędzi, a każdy podzbiór wierzchołków ma dużo sąsiadów.
Wierzchołki grafów supersinu izogenii reprezentują supersingularne krzywe eliptyczne nad ciałami skończonymi,
a krawędzie grafów - izogenie między tymi krzywymi.
