# Bookkeeping Assistant

Natural-language assistant for bookkeeping data. Users ask questions in plain English; the API classifies intent, generates safe SQL, queries the database, and streams an LLM answer.

## Overview

FastAPI service that combines:

- Intent classification and SQL generation with Gemini
- Schema-aware query building with conversation memory
- Guardrails that reject unsafe SQL
- Streaming chat responses

## Getting started

```bash
cp .env.example .env
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn main:app --reload
```

Open `http://localhost:8000/docs`.

## Configuration

| Variable | Purpose |
| --- | --- |
| `DB_*` | MySQL connection |
| `GEMINI_API_KEY` | LLM access |

Never commit `.env`.

## Main endpoint

`POST /chat` with `{ "session_id": "demo", "user_input": "Show last month invoices" }`.
