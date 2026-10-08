# Dieta e spesa

App web per vedere il pasto del momento e la lista della spesa della settimana. Funziona su iPhone, tablet e computer, anche senza connessione. La dieta resta solo sul dispositivo: questo repository contiene l'app, non i tuoi dati.

File:

- `index.html`: l'app
- `manifest.webmanifest`: nome e icona per l'installazione
- `sw.js`: copia locale per l'uso offline
- `icona.png`: l'icona della schermata Home

## Pubblicare su GitHub Pages

1. Su github.com crea un nuovo repository, per esempio `MyDiet`, impostato come **Public**.
2. Nella pagina del repository scegli **uploading an existing file**, trascina tutti i file di questa cartella e conferma con **Commit changes**.
3. Vai in **Settings → Pages**. In **Source** scegli **Deploy from a branch**, poi branch **main** e cartella **/ (root)**, e salva.
4. Dopo uno o due minuti l'app è online su `https://rojo-66.github.io/MyDiet/`.

## Installarla sull'iPhone

1. Apri l'indirizzo in **Safari**.
2. Tocca **Condividi → Aggiungi alla schermata Home**. Se compare l'opzione **Apri come app web**, lasciala attiva.
3. Apri l'app **dall'icona** e importa lì il file della dieta. Safari e l'app sulla Home hanno memorie separate: quello che importi in Safari non si vede nell'app.

## Cambiare l'icona

1. Prepara un'immagine PNG quadrata, almeno 512 × 512 pixel, senza angoli arrotondati (li aggiunge iOS).
2. Chiamala `icona.png` e caricala nel repository al posto di quella attuale.
3. iOS salva l'icona quando la aggiungi alla Home, quindi va reinstallata. **Prima esporta la dieta**: eliminando l'icona dalla Home, iOS cancella anche i dati dell'app. Poi elimina l'icona, aggiungila di nuovo da Safari e reimporta il file.

## Aggiornare l'app

Carica nel repository il nuovo `index.html` al posto del vecchio. Alla prima apertura con connessione l'app usa la versione nuova; la dieta salvata sul dispositivo resta.
