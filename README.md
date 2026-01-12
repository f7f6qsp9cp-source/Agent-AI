# Agent AI (MVP)

Szkic projektu Agent AI — backend w FastAPI, Redis (queue/cache) i Postgres.

Quickstart:
- Skopiuj `.env.example` → `.env` i uzupełnij klucze (np. `OPENAI_API_KEY`)
- docker compose up --build
- Frontend: (do dodać)

Endpoints:
- GET /health
- POST /api/v1/chat
- POST /api/v1/search

Search example (curl):

```bash
curl -X POST http://localhost:8000/api/v1/search \
  -H "Content-Type: application/json" \
  -d '{"query": "Stable Diffusion tutorial"}'
```

Search uses SerpAPI (Google engine) when `SERPAPI_API_KEY` is configured; results are cached for `CACHE_TTL_SEARCH` seconds (default 1800 = 30 minutes).

Następny krok: implementacja integracji z OpenAI/Bing i endpointu chat z zarządzaniem kontekstem.
