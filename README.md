# Il Nodo di Dara

Sito ufficiale della mostra fotografica di Elisabetta Acquaviva sulla menopausa.
Museo della Città di Rimini · 7 marzo – 10 maggio 2026.

**www.ilnododidara.com**

---

## Architettura

Sito statico HTML/CSS/JS — nessun framework, nessun bundler.
Deploy automatico via **Cloudflare Pages** dal branch `main` (~30 secondi).
Asset pesanti (audio, foto foresta) su **Backblaze B2**.

## Struttura cartelle

```
/                     → Home
/progetto             → Il Progetto
/foresta-sospesa      → La Foresta Sospesa (91 ritratti)
/eco                  → L'Eco (hub)
  /dediche            → Il libro delle dediche
  /testimonianze      → Voci dei partecipanti
  /storie-social      → Reel e social
/eventi               → Hub eventi
/dietro-le-quinte     → Dietro le quinte (hub)
  /inaugurazione      → 7 Marzo 2026
  /allestimento       → Allestimento
  /disallestimento    → Disallestimento
/rassegna-stampa      → Press kit e articoli
/soundscape           → Accesso solo via QR in mostra
/bio                  → Hub Instagram (noindex)
/le-tue-foto          → Area privata partecipanti (noindex)
```

## Modifiche

Ogni pagina è un file `index.html` autonomo con CSS e JS inline.

Per modifiche singole: editare il file direttamente e fare commit su `main`.

Per modifiche di massa (nav, token CSS globali): usare uno script Python con regex — evitare find-and-replace manuale su 15+ file.

## Audio (Backblaze B2)

Il soundscape non è nel repository per motivi di performance.

- File: `soundscape20.mp3`
- Bucket: **Public**
- Daily bandwidth cap: $1.00 (~101 GB/giorno)

## Documentazione

- `CONTEXT.md` — architettura completa, design system, convenzioni
- `comuni-target-proposta.md` — 20 enti pubblici per la proposta di itineranza
- `nodo-dara-proposta-collaborazione.md` — lettera tipo per proposte di collaborazione
