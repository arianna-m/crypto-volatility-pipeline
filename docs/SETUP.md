# Setup

1. `cp .env.example .env` and edit if paths differ for your machine.
2. `pip install -r requirements.txt` (use a venv if you prefer).
3. **API only (CI-friendly baseline, no model pickle):** `MODEL_VARIANT=baseline uvicorn app.main:app --host 0.0.0.0 --port 8000`
4. **Full stack (Kafka, API, etc.):** from repo root, `docker compose up -d --build` (or `docker compose -f docker/compose.yaml up -d --build` if you use the stack under `docker/`).
5. **Smoke test:** `curl -s http://127.0.0.1:8000/health` → `{"status":"ok"}`
