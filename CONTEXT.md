# Nodo di Dara — Contesto Progetto

## Repository e deploy
- **GitHub**: https://github.com/maucarle/mostra-dara
- **Deploy**: Cloudflare Pages (automatico da main, ~30 secondi)
- **Dominio**: www.ilnododidara.com
- **Analytics**: Cloudflare token `6cdd8038d56f4ebfb8568bb4fe7b90b2`

## Progetto
Mostra fotografica di Elisabetta Acquaviva sulla menopausa.
Museo della Città di Rimini · 7 marzo – 10 maggio 2026.
Contatti: 333 6265276 · info@elisabettacquaviva.it

## Numeri mostra (aggiornati giugno 2026)
- **3.000** visitatori
- **667** nodi annodati
- **12** eventi e incontri
- **200** metri di nastro rosso

## Design System
```css
--oro:       #c9a96e
--oro-dim:   rgba(201,169,110,0.18)
--oro-mid:   rgba(201,169,110,0.55)
--bark:      #2c241c
--moss:      #3d3328
--white:     #f5f5f0
--white-mid: rgba(245,245,240,0.75)
--white-low: rgba(245,245,240,0.50)
--bg:        #0e0c0a
```
Font: `Cormorant Garamond` (serif italic, titoli/citazioni) · `Barlow Condensed` (uppercase tracking, nav/kicker/etichette) · `Barlow` (corpo)
Estetica: sfondo near-black · accenti oro · angoli vivi (niente border-radius) · hairline 1px · foto in grayscale con degrayscale all'hover
Breakpoint hamburger: **980px** (tutte le pagine)

## Struttura sito

### Menu principale (7 voci)
```
/                    → Home (landing)
/progetto            → Il Progetto
/foresta-sospesa     → La Foresta Sospesa (91 voci, filtro emozione + ricerca nome)
/eco                 → L'Eco  [hub — has-sub]
  /dediche           → Il libro delle dediche
  /testimonianze     → Voci dei partecipanti (masonry)
  /storie-social     → Reel e condivisioni social
/eventi              → Eventi (hub con card + Luma booking)
/dietro-le-quinte    → Dietro le quinte  [hub — has-sub]
  /inaugurazione     → 7 Marzo 2026 (video YouTube + lightbox foto)
  /allestimento      → Video allestimento (YT tiles 16:9 + masonry)
  /disallestimento   → Video disallestimento (reel 9:16 + YT tiles)
/rassegna-stampa     → Stampa (press kit, articoli)
```

### Fuori menu (intenzionali)
```
/soundscape          → Accesso solo via QR in mostra — NON toccare, NON spostare
/le-tue-foto         → Privata, noindex, accesso diretto per partecipanti
/bio                 → Hub link-in-bio Instagram (design separato, noindex)
/stampa              → Alias/redirect di /rassegna-stampa
/eventi/inaugurazione → Evento inaugurazione (diverso da /inaugurazione)
```

### Prototipi — non toccare, da rimuovere
```
foresta-sospesa2/
tenda-rossa.html
eco-proto/
foresta-sospesa-proto/
didascalie dell'anima/
```

## Navigazione — regole

### Menu has-sub
```html
<li class="has-sub">
  <a href="/eco">L'Eco</a>
  <ul class="nav-sub">
    <li><a href="/dediche">Dediche</a></li>
    <li><a href="/testimonianze">Testimonianze</a></li>
    <li><a href="/storie-social">Storie social</a></li>
  </ul>
</li>
<li class="has-sub">
  <a href="/dietro-le-quinte">Dietro le quinte</a>
  <ul class="nav-sub">
    <li><a href="/inaugurazione">Inaugurazione</a></li>
    <li><a href="/allestimento">Allestimento</a></li>
    <li><a href="/disallestimento">Disallestimento</a></li>
  </ul>
</li>
```
`.nav-sub` è nascosto su desktop, visibile nell'overlay mobile.

### Regola `active` per sottopagine
- Su `/eco` e hub: solo voce hub ha `class="active"`, nessuna sub
- Su `/dediche`, `/testimonianze`, `/storie-social`: eco ha `active` + la sub corrispondente ha `active`
- Stesso schema per `/dietro-le-quinte` e le sue sub

### Breadcrumb (solo sottopagine)
Inserito dopo `</nav>`, prima dell'hero:
```html
<div class="breadcrumb">
  <a href="/eco">← L'Eco</a>
  <span class="bc-sep">/</span>
  <span class="bc-current">Dediche</span>
</div>
```
CSS: `.breadcrumb { padding: 90px 44px 0; }` desktop · `80px 24px 0` mobile

### Sibling-bar mobile (solo sottopagine, `@media max-width: 980px`)
Prima di `</body>`:
```html
<nav class="sibling-bar" aria-label="Pagine della sezione">
  <a href="/dediche" class="active">Dediche</a>
  <a href="/testimonianze">Testimonianze</a>
  <a href="/storie-social">Storie social</a>
</nav>
```
Includere `body { padding-bottom: 56px; }` nel CSS.

La vecchia `.mob-pnav` (prev/next lineare) è stata rimossa da tutte le pagine (giugno 2026). Unica eccezione: `/soundscape` — lasciarla intatta.

## Asset remoti (Backblaze B2)
```
Audio:   https://f002.backblazeb2.com/file/SoundScape/soundscape20.mp3
Foto:    https://f002.backblazeb2.com/file/SoundScape/foto+foresta/LR_NNN_nome_MG_XXXX.jpg
```

## Asset locali struttura
```
assets/
  eventi/          → foto relatori eventi
  stampa/          → cartella-stampa.pdf + 14 JPG
  foresta-sospesa/ → foto 91 donne (alcune ancora da caricare)
  inaugurazione/   → foto inaugurazione
```

## Pagine eventi (in /eventi/[slug]/)
| Slug | Evento | Data | Luma ID |
|------|--------|------|---------|
| inaugurazione | Inaugurazione | 7 mar 2026 | — |
| la-tenda-rossa | La Tenda Rossa | 11 apr 2026 | evt-xXEUh9PqJwdIsHu |
| yoga-sabrina-rossi | Menopausa e Yoga | 21 mar 2026 | evt-M3t7fFDf9tcCFW4 |
| agopuntura-baldrati | Agopuntura e Menopausa | 22 mar 2026 | evt-gdFsxm3lZoysYqz |
| menopausa-piu-benessere | Menopausa+ Benessere | — | — |
| mi-sento-una-favola | Mi Sento una Favola | — | — |
| shooting-elisabetta | Shooting Elisabetta | — | — |
| shooting-elisabetta-2 | Shooting Elisabetta 2 | — | evt-zgZylcrECTQELMu |
| perdite-pavimento-pelvico | Perdite e Pavimento Pelvico | 19 apr 2026 | evt-SDO6HXbkNU2e1kF |
| tos-e-memoria | TOS e Memoria | — | — |

## Convenzioni tecniche
- Struttura: HTML/CSS/JS inline in ogni `index.html`, nessun bundler
- Path asset: assoluti (`/assets/[sezione]/file.jpg`)
- Foto foresta: `LR_NNN_nome_MG_XXXX.jpg` (Backblaze) o `nome.jpg` (locale)
- Luma SDK: `https://api.lu.ma/embed/sdk.js`
- Mobile nav gap: 20px, overflow-y auto, padding 80px 24px 40px
- GTM placeholder `GTM-5TX4TQJ` commentato ovunque — decommentare quando si attiva il tracking
- Per modifiche di massa (nav, CSS globale): usare script Python con regex

## File documentazione
- `CONTEXT.md` — questo file, contesto tecnico e architettura
- `comuni-target-proposta.md` — 20 enti pubblici target per la proposta itineranza (giugno 2026)
- `nodo-dara-proposta-collaborazione.md` — lettera tipo per proposta di collaborazione

## To Do
- Completare date e Luma ID per gli eventi senza booking
- Rimuovere prototipi prima del prossimo deploy (foresta-sospesa2/, eco-proto/, ecc.)
- Decidere se usare /foresta-sospesa2 al posto di /foresta-sospesa (griglia 6 colonne)
- GTM: decommentare e configurare cross-domain con elisabettacquaviva.it quando pronto
