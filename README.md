# Website Analytics Backend (Beginner Scaffold)

This repository is a beginner-friendly scaffold for a Website Analytics backend using:
- Node.js + Express
- PostgreSQL for storage
- Redis (included in compose for caching if you extend)
- Docker + docker-compose for local dev
- Swagger docs at `/api/docs`

## Quick start (local)
1. Copy `.env.example` to `.env` and edit if needed.
2. Build and run with Docker (recommended for beginners):
   ```bash
   docker-compose build
   docker-compose up -d
   ```
3. Initialize DB schema:
   ```bash
   docker exec -it $(docker ps -qf "ancestor=postgres:15") psql -U postgres -d analytics -f /app/db/init.sql
   ```
   Or run the SQL in `db/init.sql` with any Postgres client.
4. Start the Node app (if not started by compose):
   ```bash
   npm install
   npm run dev
   ```
5. Open `http://localhost:3000/api/docs` for API docs.

## What is included
- Basic API key registration & revoke (`/api/auth`)
- Event ingestion endpoint (`/api/analytics/collect`)
- Aggregation endpoints (`/api/analytics/event-summary`, `/api/analytics/user-stats`)
- Simple rate limiting via `express-rate-limit`
- Beginner-friendly code (easy to read + extend)

## Next steps / learning tasks
- Add proper owner authentication (e.g., Google Auth) to protect showing API keys.
- Implement Redis caching for expensive aggregations.
- Add background ingestion queue (e.g., BullMQ) for higher throughput.
- Add tests (Jest + supertest) — a basic test is included in `tests/` to start from.

## Run tests
```bash
npm install
npm test
```

## License
MIT
