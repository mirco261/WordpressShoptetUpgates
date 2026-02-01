# 🏁 Finálny Verdikt: WooCommerce -> Upgates / Shoptet Enterprise

Na základe analýzy pluginov, PHP kódov, multidoménovosti a .NET aplikácie sú závery nasledovné:

## 1. Technický víťaz: ✅ UPGATES
Je vhodnejší pre vašu špecifickú kombináciu požiadaviek:
*   **3 Jazyky / 3 Domény:** Zvládne to v jednej administrácii bez hackovania. Shoptet by vyžadoval 3 samostatné projekty alebo kompromisy.
*   **Dizajn:** Modul Dizajnér je najbližšia (hoci nie dokonalá) náhrada za Elementor.
*   **Strategická výhoda (API a Cena):**
    *   **Upgates:** API je v cene bežného balíka (Platinum ~150€).
    *   **Shoptet:** Pre prístup k API je nutná tarifa **Premium**, ktorá stojí cca **500 € mesačne**.
    *   *Alternatíva:* Ak by sme v Shoptete oželeli API a použili XML (16x denne), stále potrebujeme Enterprise/Premium verziu, takže nákladom sa nevyhneme.
*   **Cena:** Upgates víťazí pomerom cena/výkon. Shoptet Premium/Enterprise je násobne drahšie riešenie pre rovnaký výsledok.




## 2. Čo sa stane s vaším PHP kódom? (Kritické zmeny)
*   ❌ **Dynamic Colors (Tlačidlá podľa farby kategórie):** Toto je custom funkcionalita, ktorú **žiadny SaaS nemá v základe**. Budeme ju musieť naprogramovať znova (pomocou JavaScriptu a CSS), logika bude podobná, ale kód iný.
*   ❌ **Náhľady produktov v zozname objednávok:** Váš snippet vkladá obrázky do tabuľky objednávok. Toto **nie je možné** v SaaS systémoch natívne. Zákazník uvidí obrázky až po rozkliknutí detailu. Ide o **UI ústupok** za stabilitu systému.
*   ✅ **Štítky a Bodky:** Upgates má natívne "Štítky" a farby stavov. Nebudete na to potrebovať kód, len si ich naklikáte a priradíte farby v admine.
*   ✅ **Short Description:** Vyriešite drag&drop v Dizajnéri.

## 3. Ďalší postup (Action Plan)
1.  **Založte si Trial verziu Upgates.**
2.  **Exportujte produkty z WP:** Ideálne do XML alebo CSV (vrátane parametrov pre štítky).
3.  **Programátor .NET:** Zadajte mu úlohu: *"Potrebujeme prepísať konektor z WooCommerce REST API na Upgates API v2. Endpoint je jeden, jazyk sa rieši parametrom."*
4.  **Dizajn:** Skúste v Dizajnéri vytvoriť layout. Ak budete trvať na farbách tlačidiel podľa kategórií, počítajte s cca 5-10h práce kódera na frontend scripte.

Dokumenty na stiahnutie:
- 📄 [Detailná analýza pluginov](./detailed_plugin_analysis.md)
- 📄 [Technický plán migrácie](./migration_plan.md)
