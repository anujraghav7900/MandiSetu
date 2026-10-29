# MandiSetu — Market Intelligence & Transaction Enablement

## Run the application

Install Node.js 20 or newer. From the project root, install the root runner and each app's dependencies:

```bash
npm install
npm install --prefix frontend
npm install --prefix backend
```

Start the frontend and backend together:

```bash
npm run dev
```

The frontend is at `http://localhost:5173` and the API is at `http://localhost:4000`. Check the API at `http://localhost:4000/api/health`.

The backend starts even when MySQL is unavailable, but database-backed endpoints return `503` until a database is configured. To enable them:

1. Install and start MySQL.
2. Run `database/schema.sql` against your MySQL server.
3. Copy `backend/.env.example` to `backend/.env` and set `DB_HOST`, `DB_PORT`, `DB_USER`, `DB_PASSWORD`, and `DB_NAME` for your database.
4. Restart the backend. The health endpoint reports whether the database is connected.

The backend can also be started by itself with `npm run dev:backend`; start just the frontend with `npm run dev:frontend`.

## Status transparency

Working in the browser: navigation, sample-lot search/filter, create digital lot, net realization with separate transport/commission/storage/other costs, sell-now vs user-entered later-price scenario, FPO quantity aggregation preview, buyer trust cards, order/status updates, and dispute submission.

Simulated: mandi prices/trends, buyer verification and scores, FPO aggregation, logistics, payments, and admin data. No live market feed, trained ML model, weather/maps/payment provider, real buyer checks, or production authentication. The frontend currently uses local React state and is not connected to the API; refresh resets demo changes.
