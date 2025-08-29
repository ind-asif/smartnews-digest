# SmartNews Digest

A lightweight, mobile‑first news reader that pulls articles from free sources (RSS/NewsAPI/etc.), summarizes them via a pluggable engine (OpenAI or self‑hosted models), and shows a clean digest.

> **Why this exists**
> - Learn & practice production‑minded architecture end‑to‑end.
> - Keep vendor‑lock‑in low with a summarizer interface.
> - Ship a useful daily tool that’s easy to host on Kubernetes.

## Status
Early bootstrap. Phase 1: repo + skeleton. Next steps: scaffold `frontend` + `backend` and Docker Compose.

## Architecture (planned)


- **Path routing**: serve public UI at `/`, admin tools at `/admin`, CI at `/jenkins` (reverse proxy/ingress).
- **Retention**: store summaries for ~3–7 days initially.
- **Rate limiting**: basic limits to prevent abuse.


## Tech choices (initial)
- **Frontend**: Vite + React + Tailwind.
- **Backend**: Node.js + Fastify (TypeScript), Zod for validation.
- **Summarization**: Adapter interface (OpenAI now; swap to local/HF later).
- **Storage**: Start with SQLite, move to Postgres.
- **Container/Orchestration**: Docker, then Kubernetes (OCI) with hybrid local services.


## Roadmap
- **Phase 1**: Repo bootstrap (this), CI placeholder.
- **Phase 2**: Fetcher service (RSS/NewsAPI) + `/api/news`.
- **Phase 3**: Summarization endpoint + caching + DB.
- **Phase 4**: UI list + detail, categories.
- **Phase 5**: Rate limiting, auth for admin, deploy to K8s.


## Local development (coming soon)
- `docker compose up` will start `frontend` (5173) and `backend` (3000).


## Security & ethics
Respect publisher copyrights; show source links prominently. Cache only brief metadata and short summaries for a limited window.


## License
MIT — see [LICENSE](./LICENSE).
