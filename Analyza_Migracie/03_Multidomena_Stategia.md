# Analýza: 3 Jazyky na 3 Doménach (SK, CZ, PL)

## Požiadavka
- Jazyky: Slovenčina, Čeština, Poľština
- Domény: Každý jazyk na vlastnej doméne (napr. mojeshop.sk, mojeshop.cz, mojeshop.pl)

## 1. Upgates (Víťaz pre Multidoménu)
Upgates je známy tým, že umožňuje **multidoménovosť v rámci jednej administrácie**.
- **Ako to funguje:** Máte jeden back-end (sklad, produkty, zákazníci). V nastaveniach priradíte doménu `xyz.cz` ku češtine, `xyz.sk` k slovenčine a `xyz.pl` k poľštine.
- **Výhoda:** Všetko spravujete z jedného miesta. Sklad sa odčítava centrálne.
- **Cena:** Platíte za tarifu (napr. Gold/Platinum) + príplatok za ďalšie jazyky/domény (zvyčajne cca 15-30€/mesiac navyše za alias/jazyk).

## 2. Shoptet (Komplikovanejšie)
Shoptet štandardne funguje ako **1 e-shop = 1 projekt**.
- **Možnosť A (Cudzí jazyk):** Kúpite si doplnok "Cizí jazyky". E-shop pobeží na `mojeshop.sk`, čeština na `mojeshop.sk/cs`, poľština na `mojeshop.sk/pl`.
    - *Problém:* Toto nespĺňa požiadavku "každý má svoju doménu". (Respektíve presmerovanie z .cz na .sk/cs nie je plnohodnotná doména).
- **Možnosť B (Slovensko a Česko doplnok):** Shoptet má špeciálny doplnok pre spojenie SK a CZ verzie na samostatných doménach, ale pre Poľsko by ste pravdepodobne museli založiť **tretí samostatný e-shop**.
- **Možnosť C (Multioschod):** Mať 3 samostatné Shoptet projekty (3x mesačný poplatok) a prepojiť im sklady cez externý doplnok alebo synchronizačný mostík.
- **Výsledok:** Shoptet je pre scenár "3 jazyky na 3 rôznych doménach" administratívne aj finančne náročnejší (často znamená spravovať 3 adminy alebo platiť drahé synchronizácie).

## Záver pre vaše zadanie
Ak trváte na **3 samostatných doménach** (SEO, dôveryhodnosť trhu) a chcete to riadiť z **jedného miesta**:
-> **Upgates je technicky lepšie riešenie.**

Ak by ste ustúpili z domén a stačilo by `mojeshop.sk/pl`:
-> **Shoptet** to zvládne jedným doplnkom.
