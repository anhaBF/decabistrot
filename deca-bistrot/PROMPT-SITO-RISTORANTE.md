# PROMPT — Sito Web Ristorante/Bistrot (Single Page HTML)

Crea un sito web completo, moderno e professionale per un ristorante/bistrot.
Il sito deve essere un **singolo file HTML** (no framework, no build tools) con CSS e JS inline.

---

## DATI DEL LOCALE (sostituire con i tuoi)

- **Nome**: [NOME LOCALE]
- **Tipo**: Bistrot / Ristorante / Bar
- **Indirizzo**: [INDIRIZZO COMPLETO]
- **Telefono**: [NUMERO]
- **WhatsApp**: [NUMERO con prefisso internazionale, es. 393XXXXXXXXX]
- **Orari**: [es. Tutti i giorni 11:30 – 02:00]
- **Prenotazioni online**: [URL Quandoo / TheFork / altro]
- **Google Maps embed URL**: [URL iframe Google Maps]
- **Valutazione Google**: [es. 4.7 su XXX recensioni]
- **Prezzo medio**: [es. 20–30€ a persona]
- **Anno apertura**: [es. 2018]
- **Instagram**: [@handle]

---

## PALETTE COLORI (tema chiaro mediterraneo)

```
--bg:          #FAF3E8   (beige caldo — sfondo principale)
--bg2:         #F0E6D3   (beige scuro — sezioni alternate)
--bg3:         #E8D5B7   (beige medio — card/dettagli)
--card:        #FFFFFF   (bianco — card principali)
--gold:        #82582d   (marrone dorato — accenti e titoli)
--gold-bright: #9b6e2a   (hover accenti)
--gold-dim:    #A67840   (accenti secondari)
--text:        #3D2B1A   (marrone scuro — testo principale)
--text-muted:  #7A5430   (testo secondario)
--text-dim:    #B08050   (testo terzario / placeholder)
--border:      #E8D5B7   (bordi)
--border-2:    #D4BA90   (bordi enfatizzati)
```

---

## FONT

- **Titoli / Display**: `Playfair Display` (Google Fonts) — serif elegante
- **Body / UI**: `Karla` (Google Fonts) — sans-serif leggibile
- Importare entrambi con tutti i pesi necessari (300, 400, 500, 600, 700, italic)

---

## LOGO

Creare un **logo SVG vettoriale** circolare con:
- Cerchio esterno con bordo `#82582d` (spessore 3.5px)
- Cerchio interno decorativo sottile (opacity 0.35)
- Nome principale in grande (Playfair Display, bold) al centro
- Sottotitolo "BISTROT" sotto in caps spaziato (Karla)
- Diamante decorativo come divisore tra nome e sottotitolo
- Piccoli punti ornamentali in cima e in basso al cerchio
- Sfondo beige `#FAF3E8` interno al cerchio
- Tutto in toni `#82582d`
- Salvare come `img/logo.svg`

---

## SEZIONI DEL SITO (in ordine)

### 1. NAVBAR (fixed, sticky)
- Logo SVG (42px) + testo "Nome Locale / Città" a sinistra
- Link navigazione al centro/destra: Chi Siamo | Menu | Recensioni | Contatti
- Pulsante "Prenota" (pill dorata) che apre il **Modale Prenotazione**
- Su scroll: background bianco/beige con blur, ombra leggera
- Su mobile: hamburger menu che apre overlay fullscreen

### 2. HERO (fullscreen, 100vh)
- **Foto reale** del locale/piatti come sfondo (se disponibile), altrimenti pattern SVG maiolica siciliana
- Overlay gradiente semitrasparente caldo per leggibilità testo
- Contenuto centrato:
  - Pill badge: "Città · Indirizzo · dal Anno"
  - Nome locale in gigante (clamp 5rem → 11rem), serif bold
  - Sottotitolo "Bistrot" in italic spaziato
  - Linea decorativa verticale
  - Tagline descrittiva (2 righe)
  - 2 CTA: "Prenota un Tavolo" (bottone dorato → modale) + "Scopri il Menu" (ghost → scroll)
- Barra statistiche in basso: Rating★ | Prezzo medio | Orari | Indirizzo
- Indicatore scroll in basso a destra

### 3. CHI SIAMO
- Layout 2 colonne (testo sx, features dx)
- Sinistra:
  - Logo SVG grande (110px) centrato in cima
  - Titolo + storia del locale (3 paragrafi)
  - Pill tags: "Cucina di mare" | "Cocktail bar" | "Happy hour" | "Aperto fino alle 02:00"
- Destra:
  - Foto del piatto principale (se disponibile) con didascalia
  - 3 feature card con icona SVG + titolo + descrizione (es. Cucina, Bar, Orari)

### 4. MENU (pannello chiaro dentro sito chiaro)
- Titolo sezione
- Contenitore `menu-inner` con bordo arrotondato e ombra
- **Tab bar sticky** (si ferma sotto la navbar) con:
  - Logo + nome locale a sinistra
  - Tab: Antipasti | Primi | Secondi | Cocktails | Vini | Drinks
- **Lista piatti** per ogni categoria:
  - Layout a righe (NON card): nome + prezzo su una riga, descrizione sotto
  - Badge "Consigliato ★" inline per piatti featured
  - Header categoria con sottotitolo descrittivo
  - Hover riga: sfondo caldo che si estende a piena larghezza
- Dati menu modificabili da **pannello Admin** (vedi sotto)
- Persistenza in `localStorage`

### 5. EXPERIENCE STRIP
- 3 pannelli affiancati (min-height 380px) con gradienti colorati:
  - Pannello 1: gradiente arancio-oro → "Cucina di mare"
  - Pannello 2: gradiente blu-oceano → "Cocktail bar"
  - Pannello 3: gradiente viola-arancio → "L'atmosfera"
- Ogni pannello: numero grande (01/02/03), titolo serif, descrizione
- Hover: leggero translateY(-4px)

### 6. RECENSIONI
- Valutazione grande (es. 4.7 ★) con stelle
- Griglia 3 colonne di recensioni card:
  - Avatar con iniziale colorata
  - Nome + data
  - Stelle
  - Testo corsivo
- CTA "Lascia una recensione su Google"

### 7. PRENOTAZIONI
- Layout 2 colonne
- Sinistra: titolo + 2 opzioni cliccabili (Quandoo + Telefono) in card bianche
- Destra: form WhatsApp con campi:
  - Nome, Telefono
  - Data (min = oggi), Ora (select con pranzo/cena)
  - Numero persone (select)
  - Bottone verde WhatsApp → costruisce messaggio precompilato e apre wa.me

### 8. CONTATTI
- Layout 2 colonne
- Sinistra:
  - Logo SVG (80px)
  - Titolo "Dove siamo"
  - Lista: Indirizzo (link Maps) | Telefono | Email | Orari settimanali
  - Social buttons (Instagram, Facebook, TripAdvisor)
- Destra: iframe Google Maps (440px height, border-radius)

### 9. FOOTER
- Logo testuale + nome
- Info essenziali (P.IVA, indirizzo)
- Link "admin" quasi invisibile (font 0.55rem, opacity bassissima) → apre pannello admin

---

## MODALE PRENOTAZIONE

Si apre da **tutti** i pulsanti "Prenota" del sito tramite classe `.prenota-trig`.

Contenuto:
- Titolo "Come vuoi prenotare?"
- Icona calendario
- 3 opzioni con icona colorata + testo + sottotesto:
  1. **Prenota Online** (bottone dorato) → URL Quandoo/TheFork in nuova tab
  2. **Scrivici su WhatsApp** (bottone verde) → `wa.me/[NUMERO]?text=Ciao!%20Vorrei%20prenotare...`
  3. **Compila il modulo** → scroll alla sezione prenotazioni (chiude modale)
- Separatori "oppure" tra le opzioni
- X di chiusura, click fuori, tasto Escape
- Overlay semitrasparente con blur

---

## PANNELLO ADMIN (nascosto)

Accessibile via `#admin` nell'URL o link footer.

Funzionalità:
1. **Aggiorna menu con Claude AI**:
   - Campo API Key Anthropic (salvata in localStorage, con toggle mostra/nascondi)
   - Textarea per istruzione in linguaggio naturale (es. "Aggiungi risotto €14 nei primi")
   - Bottone "Aggiorna con Claude" → chiamata API Anthropic con header `anthropic-dangerous-direct-browser-access: true`
   - Model: `claude-sonnet-4-6`
   - Esempi rapidi cliccabili
   - Feedback visivo (ok/errore/loading)

2. **Azioni rapide**:
   - Ripristina menu originale
   - Esporta menu come JSON

3. **QR Code Menu**:
   - Genera automaticamente QR che punta a `index.html#menu`
   - Usa libreria qrcodejs da CDN
   - Pulsante "Scarica PNG"
   - Pulsante "Apri menu"

Il pannello admin mantiene **tema scuro** anche se il sito è chiaro (background `#2a1a0e`).

---

## STRUTTURA DATI MENU (JavaScript)

```javascript
const DEF = {
  antipasti: [
    { id:'a1', name:'Nome piatto', desc:'Descrizione', price:12, featured:true },
    // ...
  ],
  primi:    [ /* stessa struttura */ ],
  secondi:  [ /* stessa struttura */ ],
  cocktails:[ /* stessa struttura */ ],
  vini:     [ { ...campi base, note:'al calice' } ],
  drinks:   [ /* stessa struttura */ ],
};
```

- `featured: true` → mostra badge "★ Consigliato"
- `note` → testo piccolo in corsivo sotto la descrizione (es. "al calice", "bottiglia")
- Persistenza: `localStorage.setItem('nome_menu', JSON.stringify(menu))`

---

## ANIMAZIONI

- **Scroll reveal**: classe `.rise` (opacity 0, translateY 30px) → `.rise.in` tramite IntersectionObserver
- Delay: `.d1` → 0.1s, `.d2` → 0.2s, `.d3` → 0.3s
- **Navbar**: `#nav.stuck` allo scroll > 55px
- **Hover foto**: `scale(1.04)` su `.chi-photo:hover img`
- **Logo navbar**: rotazione 8° + scale 1.05 al hover
- Rispetta `prefers-reduced-motion`

---

## RESPONSIVE

- **1024px**: griglia chi-siamo 1 colonna, experience strip 1 colonna
- **768px**: navbar collassa in hamburger, form a 1 colonna, tab bar compatta
- **480px**: CTA hero in colonna, tab btn più piccoli
- Touch targets minimi 44px
- Nessun scroll orizzontale

---

## FOTO

- Se disponibili, usarle come:
  - **Hero**: `background-image: url(img/hero.jpg)` con `background-size: cover` + overlay gradiente caldo (rgba beige 55-96%)
  - **Chi siamo**: immagine con `aspect-ratio: 4/3`, `border-radius: 24px`, ombra, zoom al hover
  - **Menu**: foto piatti nelle card (opzionale)
- Se non disponibili: pattern SVG maiolica siciliana (sfondo beige + tratti #82582d a bassa opacità)

---

## NOTE TECNICHE

- **Zero dipendenze** (solo Google Fonts CDN + qrcodejs CDN per QR)
- **localStorage** per menu e API key
- **WhatsApp**: `https://wa.me/[NUMERO]?text=[MSG_ENCODED]`
- **Anthropic API** browser-side: header `anthropic-dangerous-direct-browser-access: true`
- **Google Maps**: iframe con `?q=[INDIRIZZO]&output=embed&z=16`
- **QR Code**: `new QRCode(el, { text: url, width: 200, height: 200, correctLevel: QRCode.CorrectLevel.H })`
- CSS custom properties per tutti i token di design
- `clamp()` per tipografia fluida
- `scroll-behavior: smooth`
- `position: sticky` per tab bar menu (top: 64px sotto navbar)

---

## OUTPUT ATTESO

1. `index.html` — sito completo (~1800 righe)
2. `menu.html` — pagina menu standalone ottimizzata per QR code (tema chiaro, no navbar/footer)
3. `img/logo.svg` — logo vettoriale circolare

Il sito deve funzionare aprendo `index.html` direttamente nel browser (no server richiesto).
