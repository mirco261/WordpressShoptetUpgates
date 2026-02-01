# Detailná analýza WordPress Pluginov

Tento dokument mapuje každý váš aktuálny plugin na riešenie v **Shoptet Enterprise** a **Upgates**.
Legenda:
- ✅ **Natívne:** Funkcia je priamo v systéme.
- 📦 **Doplnok:** Nutné inštalovať/kúpiť doplnok (v Enterprise často v cene).
- 🛠️ **Custom:** Vyžaduje úpravu kódu alebo neexistuje priama náhrada.
- ❌ **Irelevantné:** V SaaS riešení sa nerieši (cache, db cleaner, admin UI).

## 1. Dizajn a Frontend
| WP Plugin | Funkcia | Shoptet Enterprise | Upgates | Verdikt |
| :--- | :--- | :--- | :--- | :--- |
| **Elementor / Pro** | Tvorba stránok (Drag&Drop) | 🛠️ **Obmedzené.** Editácia len cez HTML bloky alebo veľmi jednoduchý editor. | ✅ **Modul Dizajnér.** Flexibilnejšie, bližšie Elementoru. | **Upgates** |

| **Classic Widgets** | Widgety | ❌ Systém má pevné rozloženie prvkov (layout). | ❌ Pevné rozloženie, konfigurovateľné cez Dizajnér. | N/A |

## 2. Marketing a SEO
| WP Plugin | Funkcia | Shoptet Enterprise | Upgates | Verdikt |
| :--- | :--- | :--- | :--- | :--- |
| **Rank Math SEO / PRO** | SEO optimalizácia | ✅ **Natívne.** Meta tagy, URL, sitemaps sú v základe. Pokročilé "score" chýba. | ✅ **Natívne.** dtto. | Remíza |
| **Brevo (Email/SMS)** | Emailing | 📦 **Doplnok.** Priame napojenie na Brevo / Mailkit. | 📦 **Integrácia.** Cez API alebo export kontaktov. | **Shoptet** (Jednoduchšie) |
| **GTM4WP** | Google Tag Manager | ✅ **Natívne.** Stačí vložiť GTM ID. Dátová vrstva je pripravená. | ✅ **Natívne.** Stačí vložiť GTM ID. | Remíza |
| **WPLoyalty** | Vernostný program | 📦 **Doplnok.** "Věrnostní systém" (veľmi prepracovaný). | ✅ **Natívne.** Bodový systém je súčasťou platformy. | **Shoptet** (Silnejšie doplnky) / **Upgates** (V cene) |
| **Product Feed ELITE/PRO** | XML Feedy | ✅ **Natívne.** Generuje feedy pre Heureku, Google, Facebook automaticky. | ✅ **Natívne.** dtto. | Remíza |
| **CookieYes** | GDPR Lišta | ✅ **Natívne.** Cookie lišta v súlade so zákonom je súčasťou systému. | ✅ **Natívne.** dtto. | Remíza |

## 3. Logistika a Platby
| WP Plugin | Funkcia | Shoptet Enterprise | Upgates | Verdikt |
| :--- | :--- | :--- | :--- | :--- |
| **Packeta** | Zásielkovňa | 📦 **Doplnok.** Zdarma, plná automatizácia (tlač štítkov). | ✅ **Natívne/Doplnok.** Plná podpora. | Remíza |
| **DPD pre WooCommerce** | DPD Kuriér | 📦 **Doplnok.** Balíkobot alebo priamy doplnok. | ✅ **Natívne/Doplnok.** | Remíza |
| **Comgate / Toret Comgate** | Platobná brána | 📦 **Doplnok.** Oficiálny doplnok Comgate. | 📦 **Doplnok.** Oficiálna integrácia. | Remíza |


## 4. Správa produktov a Objednávok
| WP Plugin | Funkcia | Shoptet Enterprise | Upgates | Verdikt |
| :--- | :--- | :--- | :--- | :--- |
| **WPML (Všetky moduly)** | Multijazyčnosť | 📦 **Custom.** Riešené cez "Cizí jazyky" alebo samostatné e-shopy. | ✅ **Natívne.** Jedna administrácia, viac jazykov/domén. | **Upgates** (Oveľa lepšie) |
| **Advanced Custom Fields (ACF)** | Vlastné polia | ✅ **Parametre.** Parametre variantov alebo filtračné parametre. | ✅ **Vlastné polia.** Konfigurovateľné polia produktov. | Remíza |
| **Min Max Control** | Limity množstva | 📦 **Doplnok.** "Minimální a maximální odběr". | ✅ **Natívne.** Nastavenie násobkov a miním. | **Upgates** (V cene) |
| **Custom Order Status Manager** | Stavy objednávok | ✅ **Natívne.** Plne editovateľné stavy a farby. | ✅ **Natívne.** dtto. | Remíza |
| **Sequential Order Numbers** | Číselné rady | ✅ **Natívne.** Nastavenie formátu čísla pre doklady/objednávky. | ✅ **Natívne.** dtto. | Remíza |
| **WooCommerce Adv. Bulk Edit** | Hromadné úpravy | ✅ **Natívne.** Hromadné úpravy v zozname produktov. | ✅ **Natívne.** dtto. | Remíza |
| **Repeat Order** | Zopakovať objednávku | 📦 **Doplnok.** "Opakovaná objednávka". | ✅ **Natívne.** V zákazníckom účte. | Remíza |
| **YITH Multi-step Checkout** | Krokový košík | ❌ **Pevné.** Štandardne 3 kroky, úprava len cez kód (Enterprise). | ❌ **Pevné.** Štandardný proces, úprava cez editor. | Remíza |

## 5. Systém a Výkon (Už nepotrebujete)
Tieto pluginy v cloude (SaaS) nahrádza samotná platforma:
- **W3 Total Cache / Redis:** O rýchlosť sa stará poskytovateľ.
- **WP-Optimize:** Databázu nespravujete.
- **Advanced Database Cleaner:** dtto.
- **Query Monitor:** dtto.
- **WPCode Lite / Temporary Login / Admin Category Tree:** Nástroje pre správcu WP, v SaaS nepotrebné.
- **Jednoduché WP SMTP:** E-maily odchádzajú zo serverov poskytovateľa (treba len nastaviť SPF/DKIM).

## 6. Analýza Vlastného Kódu (Snippets)
Tu analyzujeme vami zaslané PHP snippety a ich riešenie v novom systéme.

| Váš PHP Snippet | Funkcia | Shoptet Enterprise | Upgates | Verdikt |
| :--- | :--- | :--- | :--- | :--- |
| **Short Desc. in Cat.** | Zobraziť "Krátky popis" v zozname kategórie (pod názvom). | ✅ **Natívne / CSS.** Väčšina šablón má na to nastavenie "Zobrazit popisek v výpisu". Ak nie, stačí malé CSS/JS. | ✅ **Natívne (Dizajnér).** V module Dizajnér si do boxu produktu jednoducho potiahnete prvok "Krátky popis". | **Upgates** (Bez kódu) |
| **Dynamic Colors & Labels** | 1. Štítky (Novinka, Dopredaj) podľa atribútu.<br>2. **Farba tlačidiel podľa kategórie.** | ⚠️ **Natívne + Custom.**<br>1. Štítky = "Příznaky" (v admine).<br>2. Farby podľa kategórie = **Nie je natívne.** Treba custom JS/CSS kód, ktorý zistí ID kategórie a zmení CSS. | ⚠️ **Natívne + Custom.**<br>1. Štítky = "Štítky" (v admine).<br>2. Farby podľa kategórie = **Nie je natívne.** Riešiteľné cez JS alebo rôzne layouty. | **Remíza** (Obe vyžadujú zásah pre farby) |
| **Order Status Dots** | Farebné bodky pri stavoch objednávky v účte zákazníka. | ✅ **Natívne / CSS.** Stavy objednávok majú v Shoptete farby. Ak sa nezobrazujú v zákazníckom účte, stačí pridať 5 riadkov do "Vlastného CSS". | ✅ **Natívne / CSS.** Podobne, farby stavov sa nastavujú v admine. Prípadná úprava cez Globálne CSS je triviálna. | **Remíza** (Bezproblémové) |
| **Order History Thumbs** | Zobraziť stĺpec s fotkami produktov v zozname objednávok (Môj účet). | ❌ **Nie je natívne.** Tabuľka objednávok je systémová. Vložiť tam stĺpec a "cykliť" produkty vyžaduje hackovanie cez JS (pomalé) alebo to systém nedovolí. | ❌ **Nie je natívne.** V zozname objednávok sa zvyčajne zobrazuje len sumár. Fotky sú viditeľné až po rozkliknutí detailu objednávky. | **Strata funkcie** (UI trade-off) |
| **View Order Thumbs** | Zobraziť fotku produktu v **detaile** objednávky. | ✅ **Natívne.** Detail objednávky v Shoptete štandardne zobrazuje fotky produktov. | ✅ **Natívne.** Upgates zobrazuje v detaile objednávky miniatúry produktov automaticky. | **Upgates / Shoptet** (Bez kódu) |
| **VAT Display (ACF)** | Zobraziť informáciu o DPH podľa jazyka (ACF polia). | ✅ **Natívne.** Systém automaticky zobrazuje "Cena s DPH" / "bez DPH". Sadzbu DPH ťahá z nastavení e-shopu pre danú krajinu. Ak chcete len text, použite **Parametre**. | ✅ **Natívne.** Upgates automaticky prepočítava a zobrazuje DPH podľa krajiny zákazníka. Pre statický text stačí použiť preložený **Parameter**. | **Natívne** (Core funkcia) |
| **Admin Status Color** | Zvýrazniť stav "Čaká na platbu" žltou farbou v zozname objednávok (Admin). | ✅ **Natívne.** V nastavení stavov objednávky si vyberiete farbu (štítku alebo riadku). Prejaví sa to v admine aj u zákazníka. | ✅ **Natívne.** V nastavení stavov si priradíte farbu (HEX kód), ktorá sa používa v administrácii na vizuálne odlíšenie. | **Natívne** (Core funkcia) |
| **Admin Order Columns** | Pridať stĺpce "Poradové číslo" a "Cena s DPH" do detailu objednávky v admine. | ⚠️ **Natívne informácie.** "Cena s DPH" je v Shoptete štandard. "Poradové číslo riadku" tam nie je a nedá sa doprogramovať (uzavretý admin). | ⚠️ **Natívne informácie.** Upgates zobrazuje ceny s DPH. Vloženie stĺpca "Poradové číslo" do admin gridu nie je možné. | **Strata "Por. čísla"** (Ceny sú OK) |
| **Admin Product Visibility** | Zobraziť stĺpec "Viditeľnosť" (Katalóg/Hľadanie) v zozname produktov. | ✅ **Natívne.** Shoptet má v zozname produktov stĺpec "Viditeľnosť" (ikona oka / preškrtnuté). Filtrovanie podľa viditeľnosti je v základe. | ✅ **Natívne.** Upgates má v zozname checkbox "Aktívny". Detailnejšie stavy (len pre hľadanie) sú v detaile, ale v gride je základný stav. | **Natívne** (Core funkcia) |
| **Unit Price Check** | Prepočítať a zobraziť "Cenu za kus" pre balenia (napr. 10ks v balení). | ✅ **Natívne.** "Cena za mernú jednotku" (Unit Pricing) je povinná zo zákona a systémy ju vedia. Stačí vyplniť "obsah balenia". Zobrazí sa automaticky ("0,50 € / ks"). | ✅ **Natívne.** Zadáte "Mernú jednotku" a "Veľkosť balenia". Systém cenu prepočíta a zobrazí pod hlavnou cenou. Dizajn upravíte v Dizajnéri. | **Natívne** (Core funkcia) |
| **ACF Cat. Inheritance** | Dediť obsah poľa (napr. blog) z nadradenej kategórie, ak je v aktuálnej prázdne. | ❌ **Nie je natívne.** SaaS platformy nerobia "rekurzívne dedenie" polí v reálnom čase. | ❌ **Nie je natívne.** Ak chcete, aby sa obsah zobrazil v podkategórii, musíte ho tam zadať. | **Data Migration** (Vyriešiť pri importe) |
| **Brand Desc. on Product** | Zobraziť popis výrobcu (Značky) priamo na stránke produktu. | ⚠️ **Natívne dáta / Custom zobrazenie.** Popis značky v systéme existuje, ale štandardne sa zobrazuje na stránke "Značky", nie pri produkte. Na detail produktu treba dorobiť (šablóna/JS). | ⚠️ **Natívne dáta / Custom zobrazenie.** Upgates má popis výrobcu. Jeho vypísanie priamo do detailu produktu (nie len odkaz) vyžaduje úpravu v Dizajnéri alebo kódom. | **Custom Layout** (Možné) |
| **WPML Translations** | Preklad systémových textov (napr. Nadpis "Súvisiace produkty"). | ✅ **Natívne.** V sekcii "Preklady" (Slovník) si pre každé slovo v šablóne môžete napísať vlastný text pre každý jazyk. | ✅ **Natívne.** V sekcii "Texty a preklady" máte prístup ku všetkým systémovým hláškam a tlačidlám. Jednoducho prepíšete. | **Natívne** (Core funkcia) |
| **WPML Auto-Translate** | Automatický strojový preklad produktov (DeepL/Google) priamo v admine. | 📦 **Doplnok LOCO / Conviu.** Pre Shoptet je top voľbou **LOCO** (špecialista na preklady) alebo **Conviu** (komplexný nástroj na feedy + preklady). Oba používajú AI/DeepL a šetria náklady pamäťou. | 📦 **Integrácia DeepL.** Upgates má v Marketplace priamu integráciu na **DeepL**. Preklady sa robia buď hromadne (cez export/import workflow) alebo cez API konektory tretích strán. | **LOCO / Conviu** (Addon) |


| **Related from Deepest Cat.** | Zobrazovať súvisiace produkty z "najhlbšej" kategórie (najviac špecifickej). | ✅ **Natívne (cez Hlavnú kategóriu).** Shoptet generuje súvisiace produkty z "Hlavnej kategórie". Ak nastavíte najhlbšiu kategóriu ako hlavnú, správa sa to rovnako. | ✅ **Natívne (cez Hlavnú kategóriu).** Upgates tiež viaže automatické súvisiace produkty na "Hlavnú kategóriu" produktu. Stačí správne nastaviť dáta. | **Natívne** (Data Setup) |















## Zhrnutie
Väčšina vašich pluginov má v **Shoptet Enterprise** aj **Upgates** priamu náhradu.
- **Kritický rozdiel** zostáva v **WPML (Jazyky)** a **Elementore (Dizajn)**, kde Upgates vedie architektúrou.
- **Marketingové pluginy** (WPLoyalty, Brevo) má Shoptet často lepšie pokryté "klikacími" doplnkami, ale Upgates to dobieha natívnymi funkciami.

