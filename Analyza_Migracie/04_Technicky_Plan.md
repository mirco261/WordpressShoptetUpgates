# Technický plán migrácie (WooCommerce -> Shoptet Ent. / Upgates)

## Fáza 1: Príprava dát (WooCommerce)
Než začneme migrovať, musíme dáta "upratať".
1.  **Export Produktov:**
    - Použiť plugin *Product Import Export for WooCommerce* alebo štandardný CSV exportér.
    - **Kľúčové polia:** Názov, Popis, SKU (kód), Cena, DPH, URL (pre redirecty), Obrázky, Parametre (veľkosť, farba), Kategória.
2.  **Export Zákazníkov (Cleanup):**
    - **Stratégia:** Neexportovať tabuľku `wp_users`, ale vytiahnuť unikátne e-maily a adresy z **Histórie objednávok**.
    - **Cieľ:** Preniesť len reálnych zákazníkov, ktorí nakúpili. Odstrániť prázdne/spamové "registrácie" bez objednávok.
    - *Poznámka:* Heslá sa **nedajú** preniesť (sú hashované). Zákazníci si budú musieť vygenerovať nové heslo pri prvom prihlásení.
3.  **Mapovanie URL (SEO Critical):**
    - Vygenerovať zoznam všetkých aktívnych URL adries z WooCommerce (`sitemap.xml`).
    - Pripraviť prevodovú tabuľku: `Old URL` -> `New URL`.
4.  **Upratanie Obsahu (Elementor/HTML):**
    - **Problém:** Elementor ukladá obsah obalený v množstve `<div>` a shortcodov. To v novom editore spôsobí "rozbitie" textu.
    - **Riešenie:**
        - **Produkty (Popisy):** Ak sú v Elementore, treba ich vyexportovať a prehnať cez "HTML Cleaner" (odstrániť triedy a divy, nechať len základné formátovanie `p, h2, ul, strong`).
        - **Články/Stránky:** Texty skopírovať, ale layout (stĺpce, obrázky) bude treba **manuálne vyskladať** v novom Dizajnéri.
    - **Odporúčanie:** Ideálne migrovať "čistý text" a formátovať nanovo, než prenášať "tag soup" z Elementoru.
5.  **Preklady (Stratégia):**
    - **Migrácia:** Keďže ste používali WPML, preklady už **máte v databáze**. Najlepšia cesta je vyexportovať CSV, ktoré obsahuje stĺpce pre všetky jazyky (napr. `Name_SK`, `Name_CS`, `Name_PL`). Importér Upgates/Shoptet to potom natiahne naraz. Nestrácajte čas novým prekladom.
    - **Nové produkty (Automatizácia):**
        - **Pre Shoptet:** Odporúčam doplnok **LOCO** (špecialista na preklady) alebo **Conviu** (ak chcete nielen prekladať, ale aj upravovať XML feedy pre porovnávače). Oba nástroje používajú AI a majú "pamäť", takže neplatíte za opakujúce sa vety.
        - **Pre Upgates:** Využite integráciu **DeepL** z Marketplace (kategória Komunikácia). Umožňuje prekladať popisy, ale pozor na HTML formátovanie (treba skontrolovať).

## Fáza 2: Nastavenie novej platformy
Tu sa postup líši podľa výberu.

### Cesta A: Upgates
1.  **Založenie:** Vytvoriť projekt, aktivovať multilang (SK, CZ, PL).
2.  **Import:**
    - Použiť natívny XML/CSV importér v Upgates.
    - Napárovať stĺpce z WooCommerce CSV na polia Upgates.
3.  **Dizajn:**
    - V module Dizajnér vyskladať HP a produktovú stránku (náhrada Elementoru).

### Cesta B: Shoptet Enterprise
1.  **Založenie:** Aktivácia Enterprise projektu.
2.  **Import:**
    - Využiť "Import produktov" (XLS/XML).
    - Alternatíva: Ak máte Enterprise, Shoptet onboarding tím často pomôže s migráciou dát.
3.  **Automatizácia:**
    - Nastaviť XML feed pre aktualizáciu skladu (interval 1h - 1.5h, aby sme sa zmestili do 16x denne).

## Fáza 3: Úprava .NET aplikácie
Aplikácia, ktorá synchronizuje sklad z ERP.

1.  **Zmena Logiky:**
    - Prepísať výstupný modul z `WooCommerce REST API` na cieľové API/XML.
2.  **Identity Mapping:**
    - Zabezpečiť, aby aplikácia vedela, že produkt s ID `123` v ERP je produkt s kódom `SKU-123` v e-shope. (Odporúčam párovať cez **SKU/Kód**, nie interné ID).
3.  **Testovanie:**
    - Spustiť update cien na testovacej verzii e-shopu. Overiť, či sa zmenila cena a sklad.

## Fáza 4: SEO a Spustenie
1.  **Nastavenie Presmerovaní (Redirects 301):**
    - Nahrať CSV tabuľku starých a nových URL do administrácie (Obe platformy podporujú import redirectov).
2.  **Meracie kódy:**
    - Vložiť GTM, GA4, Pixel ID.
3.  **DNS Zmena:**
    - V čase T (napr. v noci) zmeniť A záznamy domén na servery Shoptetu/Upgates.

## Checklist pred spustením
- [ ] Produkty importované (vrátane variantov)
- [ ] Ceny a DPH sedia
- [ ] Doprava a Platby (Comgate) nakonfigurované
- [ ] .NET aplikácia správne aktualizuje sklad
- [ ] Redirecty sú nahraté
- [ ] E-maily (SMTP) nastavené
