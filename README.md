# Dieta

App web per vedere la cena di ogni giorno della settimana. Da domenica a giovedì la cena comprende anche il pranzo del giorno dopo, con le quantità da cucinare. Un interruttore sceglie tra **cena post allenamento** e **cena senza allenamento**. Funziona su iPhone, tablet e computer, anche senza connessione. La dieta resta solo sul dispositivo: questo repository contiene l'app, non i tuoi dati.

File:

- `index.html`: l'app
- `manifest.webmanifest`: nome e icona per l'installazione
- `sw.js`: copia locale per l'uso offline
- `icona.png`: l'icona della schermata Home

## Il file della dieta

L'app importa un file `.json` nel formato 3 di Healthy App (`schemaVersion: 3`). Usa solo:

- `products`: nome e unità (`g`, `ml`, `pz`) di ogni alimento;
- `days`: 7 giorni (`weekday` da 1 = lunedì a 7 = domenica), con `defaultType` e le varianti `gym` (post allenamento) e `rest` (senza allenamento). Di ogni variante legge la `cena`, il `pranzo` e la `note`; le varianti `run` vengono ignorate;
- `recipes`: le ricette collegate alla cena o al pranzo.

L'interruttore parte dal `defaultType` del giorno (`gym` = post allenamento, tutto il resto = senza allenamento). Le scelte fatte valgono per la settimana in corso e il lunedì si azzerano. Se un giorno ha una sola variante, l'interruttore resta bloccato su quella.

## Pubblicare su GitHub Pages

1. Su github.com crea un nuovo repository, per esempio `MyDiet`, impostato come **Public**.
2. Nella pagina del repository scegli **uploading an existing file**, trascina tutti i file di questa cartella e conferma con **Commit changes**.
3. Vai in **Settings → Pages**. In **Source** scegli **Deploy from a branch**, poi branch **main** e cartella **/ (root)**, e salva.
4. Dopo uno o due minuti l'app è online su `https://rojo-66.github.io/MyDiet/`.

## Installarla sull'iPhone

1. Apri l'indirizzo in **Safari**.
2. Tocca **Condividi → Aggiungi alla schermata Home**. Se compare l'opzione **Apri come app web**, lasciala attiva.
3. Apri l'app **dall'icona** e importa lì il file della dieta (**Impostazioni → Importa dieta**). Safari e l'app sulla Home hanno memorie separate: quello che importi in Safari non si vede nell'app.

## Cambiare l'icona

1. Prepara un'immagine PNG quadrata, almeno 512 × 512 pixel, senza angoli arrotondati (li aggiunge iOS).
2. Chiamala `icona.png` e caricala nel repository al posto di quella attuale.
3. iOS salva l'icona quando la aggiungi alla Home, quindi va reinstallata: elimina l'icona, aggiungila di nuovo da Safari e reimporta il file della dieta (eliminando l'icona, iOS cancella anche i dati dell'app).

## Aggiornare l'app

Carica nel repository il nuovo `index.html` al posto del vecchio. Alla prima apertura con connessione l'app usa la versione nuova; la dieta salvata sul dispositivo resta.
