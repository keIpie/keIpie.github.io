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

Wybrana struktura algebraiczna to pierścień modulo wielomian cyklotomiczny: $\mathbb{Z}_q[x]/(x^{256}+1)$.

### [NTRU](https://ntru.org/) - KRATY

NTRU używa kratowego problemu NTRU w kratach cyklicznych.

### [SABER](https://www.esat.kuleuven.be/cosic/pqcrypto/saber/) - KRATY

SABER używa kratowego problem LWR - learning with rounding.
