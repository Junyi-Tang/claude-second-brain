# Claude Persistent Memory

> This file is auto-loaded at every session start. Keep it concise.
> **At the end of each session (or when new things are learned), update the relevant section below.**
> Do NOT add ephemeral task details — only facts that are useful across future sessions.

---

## User Profile

<!-- Customize: your role, background, research interests -->
- **Role:** [Your role — e.g., PhD student, researcher, engineer]
- **Background:** [Your background — e.g., field, expertise level]
- **Current focus:** [Main project or research area]

---

## Key Paths

| What | Path |
|---|---|
| **Obsidian vault** | `[PATH_TO_YOUR_VAULT]` |
| **AI Workspace wiki** | `[PATH_TO_YOUR_VAULT]/AI_Workspace/wiki/` |

---

## Behavior Rules

- **Responses:** Concise and terse. No trailing summaries.
- **Token economy:** Targeted diffs only; no full-file rewrites. Read large files once.
- **Notes destination:** Always save to Obsidian vault at the path above.

---

## Memory System Protocol

### Default Vault Check (no trigger needed)

When the user asks about **[YOUR_DOMAINS — e.g., research, methodology, course material]**, automatically check the Obsidian vault before answering from general knowledge. Steps:

1. Read `[PATH_TO_YOUR_VAULT]/AI_Workspace/meta/vault-map.md` to identify relevant folders.
2. Grep/search the relevant folders for the topic.
3. Read the most recent matching files.
4. Answer using the user's own notes, citing file paths. If the vault has nothing, say so and answer from general knowledge.

The vault is at `[PATH_TO_YOUR_VAULT]`. Key locations:
- `AI_Workspace/wiki/methods/` — standalone methodology pages
- `AI_Workspace/wiki/` — curated knowledge
- `Research/Meetings/` — meeting notes (read latest first)

### Trigger-Based Operations

For explicit vault operations, use trigger keywords. Do not execute these unless a trigger fires:

- **"query vault"** or **"ask the vault"** → deep search across the full vault, read multiple files, synthesize.
- **"log this"** or **"note this"** → append a dated entry to the relevant wiki page.
- **"ingest"** or **"update wiki"** → create/update wiki pages from new information.
- **"lint vault"** → scan for broken links, orphans, contradictions.

When any trigger fires, you must:

1. Read the universal rules at `[PATH_TO_YOUR_VAULT]/AI_Workspace/meta/instructions.md`.
2. Read `[PATH_TO_YOUR_VAULT]/AI_Workspace/meta/index.md` and `[PATH_TO_YOUR_VAULT]/AI_Workspace/meta/vault-map.md`.
3. Execute the request exactly per those rules.
4. Update `index.md` if any wiki files were created or modified.
5. Report back with a summary of changes (or a summary of findings, for query and lint).

If a request is ambiguous about which operation to run, ask before acting rather than guessing.
