# Redirect dinamico per NFC / QR (più dispositivi)

Ogni targhetta ha un link fisso e una destinazione che puoi cambiare quando vuoi, senza toccare la targhetta.

- `index.html` → reindirizza in base al dispositivo (`?d=1`, `?d=2`, ...)
- `admin.html` → pannello per gestire dispositivi e destinazioni
- `config.json` → elenco dispositivi e URL attuali

## Installazione

1. Carica i 4 file nel repository `QR-App` (pubblico).
2. **Settings → Pages**: *Deploy from a branch*, branch `main`, cartella `/ (root)`, **Save**.
3. Il sito è su `https://acla97.github.io/QR-App/`.

## Token (una volta sola)

1. GitHub → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. *Repository access*: **Only select repositories** → `QR-App`.
3. *Repository permissions → Contents*: **Read and write**.
4. Copia il token (`github_pat_...`).

## Uso

1. Apri `https://acla97.github.io/QR-App/admin.html`.
2. Incolla il token la prima volta (resta solo sul tuo dispositivo).
3. Per ogni attività: dai un nome, incolla la pagina recensioni Google, premi **Salva tutto**. Puoi anche personalizzare il **codice del link** (per esempio `bar-roma` al posto di `1`): il link diventa `https://acla97.github.io/QR-App/?d=bar-roma`. Se cambi un codice già usato in una targhetta, il vecchio link smette di funzionare.
4. Copia il **link fisso** del dispositivo (es. `https://acla97.github.io/QR-App/?d=1`) e inseriscilo nel sito del produttore di quella targhetta.
5. Per cambiare destinazione in futuro: stesso pannello, modifica l'URL e premi **Salva e verifica**. Sotto il pulsante compare il link **Prima** e quello **Ora**, poi il pannello controlla il sito pubblicato e mostra **Online ✓** quando il nuovo link è davvero attivo (di solito circa 1 minuto).

## Note

- Non condividere il token.
- Il repo è pubblico: gli URL di destinazione sono leggibili da chiunque.
- Nessuna statistica sulle scansioni.
