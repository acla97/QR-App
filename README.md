# Redirect dinamico per NFC / QR

Una pagina che reindirizza a un URL che puoi cambiare quando vuoi, senza toccare la targhetta.

- `index.html` → l'indirizzo fisso da mettere nella targhetta (reindirizza)
- `admin.html` → pannello per cambiare la destinazione
- `config.json` → contiene l'URL attuale

## Installazione (5 minuti)

1. Crea un repository **pubblico** su GitHub (es. `link`) e carica questi 4 file.
2. Vai su **Settings → Pages**, scegli *Deploy from a branch*, branch `main`, cartella `/ (root)`, poi **Save**.
3. Dopo un minuto il sito è online su `https://TUOUTENTE.github.io/link/`.
   **Questo è l'URL da inserire nel sito del produttore della targhetta.**

## Creare il token (una volta sola)

1. GitHub → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. *Repository access*: **Only select repositories** → scegli il repo.
3. *Permissions → Repository permissions → Contents*: **Read and write**.
4. Copia il token (`github_pat_...`).

## Cambiare il link

1. Apri `https://TUOUTENTE.github.io/link/admin.html` (anche da telefono).
2. Incolla il token la prima volta (resta salvato solo sul tuo dispositivo).
3. Scrivi il nuovo URL e premi **Salva**. Attivo in circa 1 minuto.

## Note

- Non condividere il token: chi lo ha può modificare il repository.
- Il repo è pubblico, quindi anche l'URL di destinazione è leggibile da chiunque (è comunque visibile a chi scansiona).
- Nessuna statistica sulle scansioni (GitHub Pages è statico).
