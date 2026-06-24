---
type: reference
created: "YYYY-MM-DD"
modified: "YYYY-MM-DD"
description: "Vault-wide directory map — what's where"
tags:
  - ai-workspace
  - meta
---
# Vault Map

> [!abstract] Purpose
> Static directory of every folder in the vault. Claude reads this first during queries to locate relevant material. Contains no file counts or dates — use Glob/Grep to discover specific files within folders.

---

## AI_Workspace (curated knowledge layer)

| Folder | Description |
|---|---|
| `AI_Workspace/wiki/projects/` | Thin project routing pages — link to methods, decisions, people, raw notes |
| `AI_Workspace/wiki/methods/` | Standalone, project-agnostic methodology knowledge |
| `AI_Workspace/wiki/decisions/` | Decision graves per project — why choices were made |
| `AI_Workspace/wiki/people/` | Collaborator preferences, feedback patterns |
| `AI_Workspace/wiki/tools/` | Environment and tool knowledge |
| `AI_Workspace/wiki/` (root) | Legacy wiki pages (being migrated to subdirs) |
| `AI_Workspace/meta/` | Instructions, indexes, vault map, changelog |
| `AI_Workspace/sources/` | Read-only raw materials |

---

## Raw Notes

> [!note] Customize this section
> Replace the folder descriptions below with your own vault structure.

| Folder | Description |
|---|---|
| `Research/Meetings/` | Meeting notes (chronological). **Read latest first.** |
| `Research/Projects/` | Project-specific raw notes |

---

## Query Rules

1. Read this vault map first to identify relevant folders.
2. Use Glob/Grep to find specific files within those folders.
3. For research questions: `AI_Workspace/wiki/` (curated) → raw notes.
4. **Recency:** when multiple files cover the same topic, read the most recent first (check filenames for dates). Earlier files provide context only if the latest is ambiguous.
5. For meeting-related questions: read from latest backward.
6. For methodology questions: `AI_Workspace/wiki/methods/` — standalone explanations.
7. **Source routing:** when the user asks about discussions, debates, or opinions, go to the raw source (meetings, people/, decisions/) — not the wiki summary. The wiki summary is for status; the raw notes are for what actually happened.
