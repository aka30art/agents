# AGENT OS — Professional Specialist Prompt Library

## Product definition
AGENT OS is a local-first library of reusable professional role prompts. Each specialist profile provides a complete master prompt that the user copies into ChatGPT or another AI assistant.

**AGENT OS does not run AI models, create autonomous agents, orchestrate tasks, call model APIs or require Ollama.** It is a prompt directory and management workspace. The user chooses the AI platform and controls every interaction.

## Included
- 160 curated specialist roles across 16 professional disciplines.
- Search by profession, role, expertise and discipline.
- Department filtering, favourites and recently opened specialists.
- Complete generated master prompt for every specialist, including professional identity, expertise, operating principles, discipline-specific method, task/context placeholders and expected deliverable.
- One-click copy of the complete specialist prompt.
- Prompt Workshop for creating custom specialist roles and instruction sets.
- Prompt Vault for storing, editing, copying and deleting full reusable prompt templates.
- Project reference areas for DOP Brand, AKASHI Art, SPECTRA TCG, SKIP HIRE TYCOON, DOWNTIME and AI Prompt Library.
- IndexedDB persistence, migration of earlier localStorage data and versioned JSON export/restore.

## The 16 disciplines
1. Strategy & Intelligence
2. Creative & Art
3. Graphic Design & Illustration
4. Web & Digital Products
5. Brand & Marketing
6. Photography, Video & 3D
7. Music & Audio
8. Writing & Publishing
9. Business & Commerce
10. E-commerce & Retail
11. Industrial & Operations
12. Technology & Software
13. AI & Automation
14. Data & Research
15. Education & Learning
16. Gaming & Collectibles

These categories focus on professional knowledge work and creative/technical disciplines, not manual-trade job roles.

## Use
1. Open Specialist Directory.
2. Search or filter for the professional role you need.
3. Open its profile and review the master prompt.
4. Select **Copy Full Specialist Prompt**.
5. Paste it into ChatGPT or another AI assistant.
6. Replace the task, context and constraint placeholders with your brief.

## Local data architecture
- IndexedDB database: `agent-os-local`
- Object store: `workspace`
- Workspace records: specialist profiles, favourites, recent profiles and full Prompt Vault entries.
- Existing localStorage records are migrated when the IndexedDB database is empty.
- Earlier AGENT OS backup files remain importable.
- JSON backups include a format identifier, schema version, export timestamp and complete local prompt library.

Data stays in the browser profile. It is not synchronised between devices or uploaded to an external service. Export backups regularly.

## Run locally
Open `index.html` in a modern browser or run:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Explicit exclusions
- No autonomous agent execution.
- No Ollama or local model runtime.
- No hosted AI APIs or model calls.
- No multi-agent orchestration.
- No paid backend, database subscription or account requirement.

AGENT OS supplies professional prompts; the user's chosen AI assistant performs the actual AI interaction.
