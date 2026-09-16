# Juan Pablo Figueroa

**AI & Data Engineer** · Santiago, Chile · Google Cloud certified

I work at the point where data engineering meets applied AI. Ten years building
production data pipelines on GCP, and the last two shipping RAG systems that are
measured rather than demoed.

The thing I care about: an AI system you can't evaluate is a prototype, whatever
it is running on. Retrieval quality belongs in CI next to the unit tests.

---

## What I've built

**Industrial RAG in production** — On-premise system for a manufacturing client
in Spain. Operators query machine manuals, maintenance procedures and captured
plant knowledge from tablets on the floor.

- ~16,000 queries in a 7-day window
- RAGAS faithfulness **0.96 median**, context precision **0.997**, captured
  weekly from production and versioned as baselines
- **307 automated tests** and 5 CI pipelines — tests, security, regression,
  retrieval eval, baseline capture
- 10 containers: FastAPI + SQLAlchemy async, PostgreSQL, Qdrant, Ollama,
  Celery + Redis, Vue 3 PWA, nginx, NVIDIA GPU

**Analytical platform for a national retail group** — **2,702 Dataform models**
in production across seven repositories, layered STG → DW → PUB: conformed
dimensions, fact tables, pricing and campaign domains.

**Tax and banking data extraction** — Multi-tenant service that connects
directly to Chile's tax authority and six bank portals via Playwright. 45
FastAPI routers, 162 test files, swappable adapter behind one environment
variable so the downstream contract never changes.

**Real-time voice agent** — Twilio → Deepgram → Groq → Cartesia, bidirectional
mulaw/8000 audio over WebSocket with a jitter buffer. Spanish-language
collections and customer service.

---

## Public code

Two repositories extracted from production systems — the transferable parts,
with the hard decisions documented:

**[rag-hybrid-citations](https://github.com/jpfiguer/rag-hybrid-citations)**
Hybrid RAG on Postgres + pgvector. Dense and BM25 fused with Reciprocal Rank
Fusion inside SQL, citations that carry document, page and section so a reader
can verify them, and an explicit refusal path for when the corpus doesn't hold
the answer. Its `DECISIONS.md` covers eight bugs paid for in production —
including three chained failures where each fix caused the next.

**[surveybq-engine](https://github.com/jpfiguer/surveybq-engine)**
CSAT/NPS survey engine with no dependencies and no build step. Responder,
visual editor, analytics panel, BigQuery output. Static files, because whoever
scans a QR code arrives on a clean browser, on some phone, sometimes without
signal — every kilobyte and every build step is a way for that to fail.

Reference implementations of patterns I use:
[gcp-etl-pipeline](https://github.com/jpfiguer/gcp-etl-pipeline) ·
[rag-crag-reference](https://github.com/jpfiguer/rag-crag-reference) ·
[multi-tenant-saas-starter](https://github.com/jpfiguer/multi-tenant-saas-starter) ·
[case studies](https://github.com/jpfiguer/portfolio)

---

## Stack

**AI** RAG in production · evaluation with RAGAS · hallucination detection ·
reranking with circuit breakers · Qdrant · pgvector + HNSW · OpenAI · Claude ·
Gemini · Mistral · Ollama · faster-whisper

**Data** BigQuery · Dataform · DBT · Apache Beam · Dataflow · Pub/Sub · Airflow ·
Polars · PostgreSQL

**Backend** Python · FastAPI · SQLAlchemy 2.0 async · Celery · TypeScript ·
Next.js · tRPC

**Ops** Docker · on-premise GPU deployment · nginx · Caddy · GCP · Vercel ·
GitHub Actions · Prometheus · OpenTelemetry · Sentry

---

Open to remote roles. Spanish native, working English.

[jpablofigueroar@gmail.com](mailto:jpablofigueroar@gmail.com) ·
[LinkedIn](https://linkedin.com/in/juan-pablo-mac-fig)
