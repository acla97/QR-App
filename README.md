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
3. Per ogni attività: dai un nome, incolla la pagina recensioni Google, premi **Salva e verifica** nella scheda del dispositivo (il token si incolla in fondo alla pagina). Puoi anche personalizzare il **codice del link** (per esempio `bar-roma` al posto di `1`): il link diventa `https://acla97.github.io/QR-App/?d=bar-roma`. Se cambi un codice già usato in una targhetta, il vecchio link smette di funzionare.
4. Copia il **link fisso** del dispositivo (es. `https://acla97.github.io/QR-App/?d=1`) e inseriscilo nel sito del produttore di quella targhetta.
5. Per cambiare destinazione in futuro: stesso pannello, modifica l'URL e premi **Salva e verifica** nella scheda di quel dispositivo. Sotto il pulsante compare il link **Prima** e quello **Ora**, poi il pannello controlla il sito pubblicato e mostra **Online ✓** quando il nuovo link è davvero attivo (di solito circa 1 minuto).

## Generare il link recensioni dal Place ID

Se non hai il link di recensione, apri **Non hai il link? Crealo dal Place ID** nella scheda del dispositivo, incolla il Place ID dell'attività (inizia di solito con `ChIJ`) e premi **Genera link**. Il link viene inserito in *Destinazione*: controllalo con **Prova** e poi premi **Salva e verifica**.

## Statistiche scansioni (facoltativo)

Usa GoatCounter, gratuito per piccole e medie attività, senza cookie e senza dati personali.

1. Crea un account su `https://www.goatcounter.com` e scegli un codice (per esempio `mio-bar`): le statistiche saranno su `https://mio-bar.goatcounter.com`.
2. In GoatCounter, nelle impostazioni del sito, aggiungi `acla97.github.io` tra i domini autorizzati a inviare dati. Se i numeri restano a zero, controlla questo punto.
3. In `admin.html` scrivi il codice nel campo **Statistiche scansioni** e premi **Salva e verifica** in una qualsiasi scheda.
4. Ogni scansione viene contata come pagina `/d/<codice del dispositivo>`, con il nome dell'attività come titolo. Per non contare le scansioni lascia il campo vuoto.

## Note

- Non condividere il token.
- Il repo è pubblico: gli URL di destinazione sono leggibili da chiunque.
- La scansione impiega al massimo 0,8 secondi in più quando le statistiche sono attive.
