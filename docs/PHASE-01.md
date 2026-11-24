# AGENT OS — Phase 01 Foundation

## Included
- Responsive industrial-tech command centre and navigation.
- Dashboard metrics and six department quick-launch tiles.
- Agent directory seeded with 14 starter specialists across six departments.
- Search across names, descriptions, capabilities and commands.
- Department filtering, favourites and recently opened agents.
- Agent profile drawer with master instructions and command shortcuts.
- Agent Workshop for creating custom agents with duplicate-name protection.
- Prompt Vault with add, copy and remove.
- Project overview for DOP Brand, AKASHI Art, SPECTRA TCG, SKIP HIRE TYCOON, DOWNTIME and AI Prompt Library.
- Activity history based on recently opened profiles.
- IndexedDB persistence for the complete local workspace.
- Versioned JSON workspace export and restore.
- Agent Runner with local Ollama discovery, model selection, streaming responses, cancellation, output copy/download and local execution history.
- Automatic one-time migration of existing localStorage records into IndexedDB.

## Run
This is a zero-build static application. Open `index.html` in a modern browser, or serve the repository locally:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Local data architecture
AGENT OS is local-first and does not require Supabase, a hosted database, account service or remote API.

- IndexedDB database: `agent-os-local`
- Object store: `workspace`
- Workspace records: agents, favourites, recent agents and prompt titles.
- localStorage is read only as a migration source when the IndexedDB database is empty.
- JSON backups include the workspace records, format identifier, schema version and export timestamp.
- Restore validates the backup format and version, asks for confirmation, then replaces the current local workspace.

Data remains in the browser profile on the device. It is not automatically synchronised between browsers or devices. Browser storage can be cleared, so users should export backups regularly and store them separately.

## Backup and restore
Open **Backup & Restore** from the sidebar.
- **Download JSON backup** exports the current workspace to a dated JSON file.
- **Choose backup file** validates and restores a previously exported AGENT OS JSON backup.
- Restoring replaces current local workspace records. Export a backup first if you need to preserve the current state.

## Local agent execution (Phase 02)
The Agent Runner sends a specialist's role, description, capabilities, master instructions and user task to Ollama running on the same computer. It uses Ollama's local HTTP API (`/api/tags` and streaming `/api/chat`). Model discovery, streaming output, cancellation, recent-run history, copy and TXT export are included.

### Setup
1. Install Ollama on the computer that will run AGENT OS.
2. Start Ollama and download at least one model using the Ollama application or CLI, for example `ollama pull qwen3:4b`.
3. Open AGENT OS in a browser on that same computer. For local development, run `python3 -m http.server 8000` and open `http://localhost:8000`.
4. Open **Agent Runner** and select **Test connection**. Choose an installed model and submit a task.
5. If the browser reports a CORS/network error, configure Ollama's `OLLAMA_ORIGINS` environment variable to allow the exact AGENT OS browser origin (for example `http://localhost:8000` or the GitHub Pages origin), then restart Ollama. Avoid broad wildcard origins unless you understand the local security implications.

The endpoint is restricted in the app to localhost/loopback addresses. Running AGENT OS on a phone while Ollama is installed on a separate computer will not work through `localhost`: localhost always refers to the device running the browser. Use the browser on the computer running Ollama.

No model is bundled. Model downloads are performed directly through Ollama. Inference remains on the local machine; AGENT OS does not send prompts to a hosted AI API.

## Remaining exclusions
Multi-agent ORCHESTRA, saved workflow execution, real file uploads and persistent project rooms remain later phases. The runner executes one specialist at a time.
