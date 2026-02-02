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

## 3. Porovnanie Trackingu a Dát (GTM / GA4 / Google Ads)
Toto je kľúčový bod pre performance marketing a vyhodnocovanie ROI.

### Upgates (Jedna administrácia = Jedna logika)
- **Centralizácia:** Keďže ide o jeden systém, dátová vrstva (DataLayer) je konzistentná pre všetky jazyky.
- **GTM & Google Ads:** Hodnoty objednávok (purchase value), meny a ďalšie parametre sa posielajú jednotným spôsobom.
    - Ak máte nastavené posielanie dát do GA4 cez GTM, preposlanie do Google Ads (konverzie) je priamočiare.
    - Nemusíte nastavovať a ladiť 3 rôzne e-shopy. Ak to funguje pre SK, bude to fungovať aj pre PL a CZ (s príslušnou menou).
- **Flexibilita:** Upgates má pomerne otvorený prístup k úprave kódov v hlavičke, čo uľahčuje nasadenie vlastných skriptov pre všetky domény naraz.

### Shoptet (Separované inštancie)
- **Rozdrobenosť:** Pri riešení formou 3 samostatných e-shopov (Možnosť C) musíte GTM a konverzné kódy nasadzovať a udržiavať **3x**.
- **Náklady na doplnky:** Kvalitná dátová vrstva (DataLayer) v Shoptete je často riešená cez externé platené doplnky. Pri 3 e-shopoch platíte tieto doplnky 3x.
- **Riziko chýb:** Pri zmenách v nastavení (napr. zmena logiky výpočtu marže pre Ads) musíte úpravu replikovať na všetkých doménach manuálne.

## Záver pre vaše zadanie
Ak trváte na **3 samostatných doménach** a potrebujete spoľahlivý **centralizovaný tracking** (posielanie hodnôt do Google Ads/GA4 bez nutnosti trojnásobnej údržby):
-> **Upgates je jednoznačný víťaz.**

Nielenže technicky zvláda domény na jednom mieste, ale aj dátová analytika a správa tagov bude výrazne jednoduchšia a menej náchylná na chyby.

Ak by ste ustúpili z domén a stačilo by `mojeshop.sk/pl`:
-> **Shoptet** to zvládne, ale stále s istými obmedzeniami v SEO a flexibilite úprav.
