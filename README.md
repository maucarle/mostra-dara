# Il Nodo di Dara - Soundscape Experience

Repository ufficiale della landing page per la mostra **"Il Nodo di Dara"**. 
Il sito è progettato per essere smart, responsive e ottimizzato per lo streaming audio immersivo tramite mobile.

## 🚀 Architettura Tecnologica
* **Hosting:** [Cloudflare Pages](https://pages.cloudflare.com/) - Banda illimitata e deploy automatico da questo repository.
* **Storage Audio:** [Backblaze B2](https://www.backblaze.com/b2/cloud-storage.html) - Hosting esterno del soundscape per non sovraccaricare il server web.
* **Framework:** HTML5 / CSS3 / Vanilla JavaScript.

## 🎧 Gestione del Soundscape
L'audio non è caricato su questo repository per motivi di performance e limiti di GitHub.
* **File Corrente:** `soundscape_dara.mp3` ospitato su Backblaze B2.
* **Ottimizzazione Mobile:** Il codice gestisce lo sblocco dell'audio tramite interazione utente (necessario per Safari e Chrome su smartphone).

### Configurazione Backblaze B2
Per garantire la continuità dello streaming:
1. Il Bucket deve essere impostato su **Public**.
2. Il **Daily Download Bandwidth Cap** è impostato a **$1.00**.
   * Questo garantisce circa **101GB** di banda al giorno (i primi 1GB sono gratuiti).
   * Costo oltre la soglia gratuita: **$0.01 per GB**.

## 🛠 Istruzioni per le Modifiche
### Aggiornare il testo o il design
1. Modificare il file `index.html`.
2. Effettuare il **Commit** delle modifiche.
3. Cloudflare Pages aggiornerà il sito live in circa 30 secondi.

### S
