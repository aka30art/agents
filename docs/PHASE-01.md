# AGENT OS — Phase 01 Foundation

## Included
- Responsive industrial-tech command centre and navigation.
- Dashboard metrics and six department quick-launch tiles.
- Agent directory seeded with 14 starter specialists across six departments.
- Search across names, descriptions, capabilities and commands.
- Department filtering, favourites and recently opened agents.
- Agent profile drawer with complete master instructions and command shortcuts.
- Agent Workshop creation form with duplicate-name protection.
- Prompt Vault with add, copy and remove.
- Project overview for DOP Brand, AKASHI Art, SPECTRA TCG, SKIP HIRE TYCOON, DOWNTIME and AI Prompt Library.
- Activity history based on recently opened profiles.
- SQL schema for PostgreSQL/Supabase with owner-scoped row-level security.

## Run
This first foundation is a zero-build static app. Open index.html locally or serve the repository:
python3 -m http.server 8000

## Persistence boundary
Agents, favourites, recent profiles and prompt titles are persisted in browser localStorage. This is browser-local only; it is not multi-device or account persistence. Apply supabase/schema.sql to a Supabase project before wiring authenticated database persistence. No Supabase credentials or model keys are included.

## Explicit Phase 01 exclusions
Agent execution, model calls, real file uploads, multi-agent ORCHESTRA, saved workflow execution and persistent project rooms are later phases. The interface labels these honestly rather than faking completed execution.
