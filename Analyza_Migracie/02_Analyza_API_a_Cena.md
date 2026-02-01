# Manažérske zhrnutie: Integrácia s .NET aplikáciou

Tento dokument porovnáva možnosti prepojenia vášho firemného systému (.NET) s novým e-shopom.
**Poznámka k Shoptetu:** Ani tarifa Enterprise **neobsahuje API** (to je súčasťou balíka Premium) a **neponúka natívnu multidoménovosť** (žiadny balík). Preto je nutné kombinovať Enterprise s Premium doplnkami alebo externe prepájať e-shopy.

## 1. Hlavné zistenie: Cena za pripojenie
Obe platformy technicky umožňujú prepojenie. Rozdiel je v **cene** a **rýchlosti**.

| Platforma | Verzia | Spôsob napojenia | Odhadované náklady* | Verdikt |
| :--- | :--- | :--- | :--- | :--- |
| **Upgates** | Platinum/Gold | **Online API (v2)** | **~80 - 150 €** | ✅ Ekonomicky výhodné |
| **Shoptet** | Enterprise | **Možnosť 1: XML** (1x hod) | ~300 € | ⚠️ Lacnejšie, ale pomalé |
| **Shoptet** | Premium | **Možnosť 2: API** (Online) | **~500 € a viac** | ❌ Vysoké fixné náklady |

*\*Ceny sú orientačné, Shoptet Enterprise je kalkulovaný individuálne.*

> **Dôležitá poznámka:** Shoptet **nemá natívnu multidoménovosť** v jednej administrácii (ani v Enterprise/Premium). Museli by sme prevádzkovať 3 oddelené e-shopy. Upgates to má v cene.

---

## 2. Detailný pohľad

### A) Upgates (Efektívna voľba)
*   **Technické riešenie:** Moderné JSON REST API (v2).
*   **Funkčnosť:** Plná podpora pre update cien, skladov a sťahovanie objednávok v reálnom čase.
*   **Biznis pohľad:** Profesionálne prepojenie získavame v rámci štandardného mesačného poplatku. Nevyžaduje žiadne dodatočné "Enterprise" príplatky.

### B) Shoptet – Možnosť 1: XML (Ekonomická voľba)
*   **Technológia:** Výmena súborov (XML import/export).
*   **Frekvencia:** Maximálne **16x denne** (cca každých 90 minút).
*   **Cena:** Postačuje tu "základný" Shoptet Enterprise (bez Premium API balíka). Odhad: ~300 €.
*   **Nevýhoda:** Sklad nie je aktuálny hneď. Hrozí predaj tovaru, ktorý sa medzitým vypredal na predajni.
*   **Verdikt:** Použiteľné, ak akceptujete oneskorenie dát.

### C) Shoptet – Možnosť 2: API (Prémiová voľba)
*   **Technológia:** REST API (Online prepojenie).
*   **Frekvencia:** Ihneď (Real-time).
*   **Cena:** Vyžaduje tarifu **Premium**, ktorá začína na cca **500 € mesačne**.
*   **Výhoda:** Rovnako kvalitné a rýchle ako Upgates API.
*   **Verdikt:** Technicky špičkové, ale ekonomicky neefektívne (platíme stovky eur navyše len za "kábel").

---

## 3. Záver pre vedenie
Z pohľadu integrácie .NET aplikácie sú obe riešenia technicky vyhovujúce. Rozhoduje "Total Cost of Ownership" (TCO):

1.  **Technicky:** Remíza. Oba systémy majú kvalitné API, ktoré náš programátor zvládne napojiť.
2.  **Ekonomicky:** **Upgates víťazí.** Poskytuje rovnakú "konektivitu" za zlomok mesačných nákladov. Pri Shoptete platíme "Enterprise prirážku" primárne za prístup k funkciám, ktoré má Upgates v základe.
