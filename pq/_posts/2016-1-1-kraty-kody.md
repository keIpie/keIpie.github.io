---
layout: post
title: Kraty, kody, q-kraty
---

kraty a kody liniowe - czym to się różni...

### kraty

kraty to $\mathbb{Z}$-moduły, czyli odpowiedniki przestrzeni liniowych nad pierścieniem $\mathbb{Z}$

### kody

kody liniowe to $k$-wymiarowe podprzestrzenie przestrzeni liniowych na ciałami skończonymi $\mathbb{Z}_q^n$.
takie kody nazywane są też kodami q-arnymi.

### q-kraty

każdemu kodowi liniowemu można jednozacznie przyporządkować kratę. kodom będącym podprzestrzeniami $\mathbb{Z}_q^n$
odpowiadają tak zwane kraty q-arne, czyli kraty $L$, dla których $q\mathbb{Z}^n \subseteq L$. z warunku tego wynika, że
wektor $x \in \mathbb{Z}$ należy do q-arnej kraty $L_q$ wtedy i tylko wtedy, gdy $x \pmod{q}$ również należy do $L_q$.

w zastosowaniach kryptograficznych można myśleć, że krat q-arne do podgrupy $\mathbb{Z}_q^n$.

w odróżnieniu od kodów q-arnych, do q-arnych krat należą nie tylko wektory $x \pmod{q}$, ale też $x$. dzięki temu
możemy rozważać euklidesową odległość.

przykładowa krata q-arna o bazie $B \in \mathbb{Z}^{n \times m}$ ma postać:
$$ L_q(B) = \{ y \in \mathbb{Z}^m ~|~ y = B s \pmod{q}~~for~some~s \in \mathbb{Z}^n~\} = B \mathbb{Z}^n + q\mathbb{Z}^m$$

odpowiada ona kodowi liniowemu o macierzy generującej $B \in \mathbb{Z}_q^{n \times m}$

### kontrola parzystości

w teori kodowania ważną rolę odgrywają macierze kontroli parzystości. dzięki nim sprawdzamy, czy dane słowo należy do kodu.

analogiczną rolę będą pełniły kraty kontroli parzystości, które można zdefiniować dla krat q-arnych (i odpowiadają macierzom
kontroli parzystości dla kodów):

$$ L_q^{\perp}(B) = \{ x \in \mathbb{Z}^m ~|~ B x = 0 \pmod{q} } $$
