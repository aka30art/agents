# AGENT OS

Personal, local-first operating system for a specialist agent ecosystem.

## Start
Open `index.html` in a modern browser, or run:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Data and privacy
AGENT OS stores workspace data in the browser using IndexedDB. It does not require Supabase, a hosted database, login or paid backend. Use **Backup & Restore** in the app to export or restore a versioned JSON workspace backup. The Agent Runner can execute specialists through [Ollama](https://ollama.com) running locally on the same computer; no cloud AI API is required.

Data is local to the browser profile and does not synchronise automatically between devices. Keep regular backups.

See [Phase 01 documentation](docs/PHASE-01.md) for implementation scope and details.

## Local AI execution
Install Ollama on your computer, download a model, open AGENT OS in a browser on that same computer, and use **Agent Runner**. If needed, allow the exact browser origin in Ollama's `OLLAMA_ORIGINS` CORS setting. See [Phase 01 and Phase 02 setup notes](docs/PHASE-01.md).
