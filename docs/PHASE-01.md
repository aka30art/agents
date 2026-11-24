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

## Explicit Phase 01 exclusions
Agent execution, model calls, multi-agent ORCHESTRA, saved workflow execution, real file uploads and persistent project rooms remain later phases. The interface labels these honestly rather than simulating completed execution.
