# AGENT OS

Personal, local-first operating system for a specialist agent ecosystem.

## Start
Open `index.html` in a modern browser, or run:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Data and privacy
AGENT OS stores workspace data in the browser using IndexedDB. It does not require Supabase, a hosted database, login or paid backend. Use **Backup & Restore** in the app to export or restore a versioned JSON workspace backup.

Data is local to the browser profile and does not synchronise automatically between devices. Keep regular backups.

See [Phase 01 documentation](docs/PHASE-01.md) for implementation scope and details.
