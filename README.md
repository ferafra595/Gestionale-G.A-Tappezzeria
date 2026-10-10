# G.A Tappezzeria — versione semplificata

Una sola cartella `public` (necessaria per separare i file accessibili dal browser dal codice privato del server).

## Struttura
- `public/`: pagina, CSS, JavaScript e loghi
- `worker.js`: API, accesso, clienti, preventivi, lavori
- `0001_init.sql`: schema database D1
- `wrangler.toml`: configurazione Cloudflare
- `package.json`: comandi di sviluppo

## Avvio
1. `npm install`
2. `npx wrangler login`
3. `npx wrangler d1 create ga-gestionale` e copia il `database_id` nel `wrangler.toml`.
4. `npm run db:remote` (per il database online) oppure `npm run db:local` (per sviluppo).
5. `npx wrangler secret put ADMIN_PASSWORD`
6. `npx wrangler secret put SESSION_SECRET` (stringa casuale lunga e segreta, diversa dalla password).
7. `npm run deploy`

Per prova locale: `npm run db:local` e `npm run dev`. I segreti per lo sviluppo locale vanno configurati separatamente in `.dev.vars` (non caricare su GitHub).

**Attenzione:** il progetto è una base applicativa, non ancora testata end-to-end in produzione. Prima di usare dati reali, verificare login, backup, numerazione, permessi e flusso di salvataggio.
