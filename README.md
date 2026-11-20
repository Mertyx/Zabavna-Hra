# 🛡️ NETGUARD // ZERO-DAY

Vzdělávací kyberbezpečnostní hra v prohlížeči, ve které se hráč ujímá role operátora bezpečnostního centra (SOC) a v reálném čase brání firemní server před síťovými útoky.

🔗 **Live verze hry:** `(https://mertyx.github.io/Zabavna-Hra/)`

---

## 🎯 Záměr projektu a řešená problematika

Cílem hry je srozumitelnou a praktickou formou vysvětlit základy **kybernetické bezpečnosti a ochrany sítí**. Místo čtení teoretických pouček si hráč v praxi vyzkouší, jak vypadá běžný i škodlivý síťový provoz, jak rozpoznat různé typy kybernetických útoků a jaký obranný mechanismus na ně použít.

Hra pokrývá 4 klíčové oblasti bezpečnosti:
1. **Šifrování přenosu (TLS / HTTPS)** – rozdíl mezi bezpečným šifrovaným spojením a nešifrovaným přenosem citlivých dat (`HTTP`, `FTP`).
2. **Phishing a sociální inženýrství** – odhalování podvodných domén (typosquatting) a škodlivých odkazů.
3. **Webové zranitelnosti (WAF)** – obrana proti útokům na webové aplikace, konkrétně **SQL Injection** a **Cross-Site Scripting (XSS)**.
4. **DDoS a zahlcení sítě (Rate-Limiting)** – ochrana serveru před botnety a masivními záplavami požadavků (`SYN Flood`, `UDP Flood`).

---

## 🎮 Zábavnost a herní principy

Aby vzdělávání nebavilo jen chvíli, je výuka postavená na principech akční tower-defense / postřehové hry:
* **Akční obrana v reálném čase:** Po 4 síťových linkách proudí k hlavnímu serveru pakety. Hráč musí rychle vyhodnotit, zda jde o legitimní provoz (který musí nechat projít), nebo o útok, který je třeba sestřelit správným modulem.
* **Inspekce paketů a maskované hrozby:** Od 3. vlny se objevují tzv. *Stealth pakety*, které se tváří nenápadně. Hráč na ně musí najet myší a přečíst si jejich skutečnou hlavičku a obsah (payload).
* **Postupný růst obtížnosti a vylepšení:** Hra má 5 vln. Mezi vlnami si hráč za získané body opravuje server nebo nakupuje vylepšení (např. automatický *Deep Packet Inspector* nebo rychlejší palbu).
* **Finální Boss (APT-26 Zero-Day):** V poslední vlně čeká pokročilý útok chráněný rotačními štíty, který prověří rychlost i znalosti ze všech předchozích vln.

---

## 📊 Měřitelnost dosaženého pokroku poznání

Hra průběžně sleduje a vyhodnocuje, jak se hráč v problematice orientuje a zda se zlepšuje:

1. **Živé znalostní skóre (%) v horní liště:** Během celé hry se počítá přesnost rozhodování (správně zvolený obranný modul vs. chybný zásah nebo zničení bezpečného HTTPS paketu).
2. **Praktické bezpečnostní mini-výzvy mezi vlnami:** Před vstupem do taktického obchodu dostane hráč reálný scénář z praxe (např. podezřelý e-mail, neošetřený SQL dotaz nebo DDoS výpadek). Správná odpověď přinese bonusové kredity i okamžité vysvětlení principu.
3. **Přechod od barev ke čtení dat (od 3. vlny):** Zatímco v prvních vlnách pomáhají barevné štítky, v pokročilé fázi musí hráč rozpoznat hrozbu čistě podle jejího technického popisu a obsahu paketu.
4. **Závěrečný report a historie pokusů (`localStorage`):** Na konci hry se zobrazí přehled úspěšnosti rozdělený podle jednotlivých kategorií útoků, aby hráč viděl, kde dělá chyby. Výsledky se ukládají v prohlížeči, takže lze porovnat zlepšení mezi jednotlivými hrami.
5. **Vestavěná Databáze hrozeb:** Kdykoliv během hry si může hráč otevřít studijní encyklopedii se reálnými ukázkami útoků a principem obrany.

---

## 🕹️ Ovládání

Hru lze ovládat kombinací myši a klávesnice (podporuje **českou i anglickou klávesnici** a numerický blok):

* **Myš + klávesnice (rychlá palba):** Najeď kurzorem na paket pro jeho inspekci a zmáčkni klávesu `1`–`4` (na české klávesnici `+`, `ě`, `š`, `č`) pro okamžitý výstřel příslušným modulem.
* **Pouze myš:** Kliknutím dole vyber obranný modul a klikni na cílový paket.

| Klávesa (CZ / EN) | Obranný modul | Proti jakým hrozbám slouží |
| :--- | :--- | :--- |
| **`+` / `1`** | **TLS Šifrování** | Nešifrovaný přenos hesel a dat (`HTTP`, `FTP`) |
| **`ě` / `2`** | **Phish Scanner** | Podvodné e-maily, falešné domény a škodlivé odkazy |
| **`š` / `3`** | **WAF / SQL Štít** | Webové útoky (`SQL Injection`, `XSS`) |
| **`č` / `4`** | **DDoS Rate-Limiter** | Zahlcení sítě (`Botnet`, `SYN Flood`, `UDP Flood`) |

---

## 🛠️ Použité technologie

* **HTML (`<canvas>`)** – vykreslování herní plochy, animací paketů, částicových efektů a vizuálního rozhraní.
* **CSS** – responzivní rozvržení obrazovky a stylování SOC panelů.
* **JavaScript** – herní smyčka, logika vln, vyhodnocování znalostí a ukládání statistik přes `localStorage`.
* **Web Audio API** – procedurální generování zvukových efektů přímo v kódu (bez nutnosti externích zvukových souborů).

---

## 🚀 Jak hru spustit

1. **Online:** Otevři odkaz na GitHub Pages uvedený v úvodu tohoto souboru.
2. **Lokálně:** Stáhni si soubor `index.html` a otevři ho v libovolném moderním webovém prohlížeči (Chrome, Edge, Firefox, Safari). Hra nevyžaduje žádnou instalaci ani server.
