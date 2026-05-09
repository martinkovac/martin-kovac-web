# Martin Kováč Hair Design — Web

**Verze:** V19 (9. května 2026)
**Stav:** Připravené k nasazení (čeká na fotky a Formspree setup)

---

## 📁 Struktura souborů

```
web_complete/
├── index.html              ← hlavní stránka (V19)
├── career.html             ← stránka kariéra s formulářem
├── cookies.html            ← zásady cookies (GDPR)
├── ochrana-udaju.html      ← ochrana osobních údajů (GDPR)
├── sitemap.xml             ← sitemap pro Google
├── robots.txt              ← instrukce pro crawlery
└── README.md               ← tento soubor
```

**Důležité:** Všechny soubory musí být ve stejné složce (root domény).

---

## 🚀 Krok za krokem před nasazením

### 1. Nastavit Formspree pro career formulář

1. Jdi na https://formspree.io/
2. Klikni **„Get Started"** (zdarma — 50 zpráv/měsíc stačí)
3. Zaregistruj se (e-mail + heslo, doporučuji pavel@eshopbooster.cz)
4. Vytvoř **New Form**:
   - **Name:** Martin Kováč — Career
   - **Send to email:** info@martinkovachairdesign.cz
5. Po vytvoření zkopíruj endpoint URL ve tvaru:
   ```
   https://formspree.io/f/abcdwxyz
   ```
6. V `career.html` najdi `YOUR_FORMSPREE_ID` a nahraď to ID ze své URL
   - Otevři career.html v editoru
   - Najdi: `action="https://formspree.io/f/YOUR_FORMSPREE_ID"`
   - Změň na: `action="https://formspree.io/f/abcdwxyz"` (s tvým ID)
7. Hotovo — první odeslaná zpráva přijde s aktivačním e-mailem od Formspree, klikni „Activate"

**Alternativně:** Pokud Marta používá Forpsi mail, můžeme udělat backend přes Apps Script (až dosadíme reálný e-mail).

### 2. Nahradit placeholder fotky

V index.html jsou placeholdery (různé pozadí + ikony) na těchto místech:
- **Hero foto** (sekce 1)
- **Martin a Renata portréty** (sekce O salonu)
- **4× kolekce fotky** (Originals, Red Woman, Pure & Wild, The Runway)
- **6× galerie fotky** (Editorial Cut, Warm Balayage, atd.)
- **3× thumb fotky** v hero (Recepce, Křeslo, Detail)
- **4× IG screenshoty** (sekce Reference)
- **4× blog thumbnaily** (sekce Blog)

Až dorazí fotky, vyměníme placeholdery za reálné. Zatím to vypadá pěkně i bez nich.

### 3. Vytvořit OG image (pro sdílení na FB/WhatsApp)

Vytvoř obrázek 1200×630px (ideálně fotka salonu nebo logo na béžovém pozadí + text), pojmenuj `og-image.jpg` a nahraj do root složky.

### 4. Nasadit na hosting

**Doporučení:** Forpsi (Marta tam pravděpodobně už má doménu)

Postup:
1. Přihlaš se do Forpsi administrace
2. V FTP klientovi (např. Cyberduck, FileZilla) se připoj k FTP účtu pro doménu martinkovachairdesign.cz
3. Nahraj **všechny soubory** ze složky web_complete do **public_html** (nebo www, podle Forpsi)
4. Test: zadej v prohlížeči `https://martinkovachairdesign.cz` a `https://martinkovachairdesign.cz/career.html`

### 5. Po nasazení — Google Search Console

1. Jdi na https://search.google.com/search-console
2. Přidej property `https://martinkovachairdesign.cz`
3. Ověř vlastnictví (např. přes DNS TXT záznam)
4. **Submit sitemap:** zadej URL `https://martinkovachairdesign.cz/sitemap.xml`

---

## ✅ Checklist před launch

- [ ] Formspree ID nahrazené v career.html
- [ ] Reálné fotky nahrané (Hero, portréty, kolekce, galerie)
- [ ] og-image.jpg nahrané
- [ ] Soubory uploadnuté na Forpsi
- [ ] Doména směřuje na nový web
- [ ] HTTPS funguje (Forpsi to obvykle dělá automaticky přes Let's Encrypt)
- [ ] Test telefonu/emailu — odkazy fungují
- [ ] Test career formuláře — pošle se test e-mail
- [ ] Sitemap submitnutý do Google Search Console

---

## 🔧 Co se dá ještě snadno přidat

- **Google Analytics 4** — měření návštěvnosti (pak je třeba doplnit do cookies.html)
- **Hotjar / Smartlook** — heatmapy, jak se uživatelé chovají
- **Facebook Pixel** — pokud bude reklama
- **Schema.org Reviews** — až budou reálné recenze, přidáme do JSON-LD

---

## 📞 Kontakt

Pro úpravy a otázky: Pavel (eshopbooster.cz)

---

*Build: V19 + Týden 1 (cookies, GDPR, sitemap, Formspree integration)*
