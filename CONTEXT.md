# Nodo di Dara — Contesto Progetto

## Repository
- GitHub: https://github.com/maucarle/mostra-dara
- Deploy: Cloudflare Pages (automatico da main)
- Dominio: www.ilnododidara.com

## Progetto
Mostra fotografica di Elisabetta Acquaviva sulla menopausa.
Museo della Città di Rimini · 7 marzo – 10 maggio 2026.
Contatti: 333 6265276 · info@elisabettacquaviva.it

## Design System
```css
--oro:       #c9a96e
--oro-dim:   rgba(201,169,110,0.18)
--oro-mid:   rgba(201,169,110,0.55)
--white:     #f5f5f0
--white-mid: rgba(245,245,240,0.75)
--white-low: rgba(245,245,240,0.50)
--bg:        #0e0c0a
```
Font: `Barlow Condensed` (titoli/nav) · `Cormorant Garamond` (italic/citazioni) · `Barlow` (corpo)

## Struttura Sito
```
/                        → landing page (countdown → CTA "Entra nella mostra")
/progetto                → descrizione mostra
/eventi                  → lista eventi con card + Luma booking
/foresta-sospesa         → 11 donne con foto + didascalia (modal al click)
/foresta-sospesa2        → layout alternativo griglia densa 6 colonne (test)
/soundscape              → pagina soundscape
/stampa                  → press kit (noindex) · PDF + 14 foto scaricabili
/rassegna-stampa         → copertura media (4 articoli)
/inaugurazione           → galleria foto+video inaugurazione (placeholder)
```

## Asset
```
assets/
  eventi/          → foto relatori eventi
  stampa/          → cartella-stampa.pdf + 14 JPG stampa
  foresta-sospesa/ → foto 11 donne (alcune ancora da caricare)
  inaugurazione/   → foto inaugurazione (da caricare)
```

## Pagine eventi (tutti in /eventi/[slug]/)
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

## Foresta Sospesa — Donne (11 caricate)
| ID | Nome | Foto |
|----|------|------|
| 06 | Silvia | silvia_MG_0818.jpg ✓ |
| 26 | Manuela | manuela_MG_7867.jpg ✓ |
| 65 | Stefania | stefania_MG_9571.jpg ✓ |
| 56 | Roberta | roberta_MG_8942.jpg ✓ |
| 43 | Eleonora | eleonora.jpg ⬆ da caricare |
| 73 | Lorella | lorella.jpg ⬆ da caricare |
| 04 | Chiara | chiara.jpg ⬆ da caricare |
| 57 | Lucia | lucia.jpg ⬆ da caricare |
| 88 | Monica | monica.jpg ⬆ da caricare |
| 87 | Eugenia | eugenia.jpg ⬆ da caricare |
| 55 | Elena | elena.jpg ⬆ da caricare |

## Rassegna Stampa (4 articoli)
1. Chiama mi Città — Web · Locale
2. Comune di Rimini — Istituzionale
3. Virgilio Notizie — Web · Nazionale
4. Geronimo News — Web · Nazionale

## Nav (ordine voci)
Home · Il Progetto · Eventi · La Foresta Sospesa · Soundscape · Stampa

## Convenzioni
- Path asset: assoluti (`/assets/[sezione]/file.jpg`)
- Foto foresta-sospesa: `nome_MG_XXXX.jpg` o `nome.jpg`
- Foto stampa: `nome_MG_XXXX.jpg` (14 file)
- Cloudflare Analytics token: `6cdd8038d56f4ebfb8568bb4fe7b90b2`
- Luma SDK: `https://api.lu.ma/embed/sdk.js`
- Mobile nav: gap 20px, overflow-y auto, padding 80px 24px 40px

## To Do
- Caricare 6 foto mancanti foresta-sospesa (eleonora, lorella, chiara, lucia, monica, eugenia, elena)
- Caricare foto inaugurazione in assets/inaugurazione/
- Caricare video inaugurazione su YouTube e aggiungere ID in inaugurazione/index.html
- Completare date/Luma ID per eventi senza booking
- Decidere se usare /foresta-sospesa2 al posto di /foresta-sospesa (griglia 6 colonne)
