# Claude Second Brain

> A structured Obsidian vault architecture that turns your notes into a queryable knowledge base for Claude Code. Claude automatically searches your vault before answering — no RAG, no vector store, no extra infrastructure.

## What This Is

A file-based "second brain" system where:

1. **Your Obsidian vault becomes Claude's memory.** When you ask about research, methodology, or anything you've written about, Claude checks your notes first.
2. **Knowledge is layered, not flat.** Methods pages are project-agnostic and reusable. Project pages are thin routing tables. Decision graves capture *why*, not just *what*.
3. **No extra tools required.** Just Obsidian + Claude Code. The vault map and CLAUDE.md do all the work.

## Architecture

```
Your Vault/
├── AI_Workspace/                    # Claude-facing knowledge layer
│   ├── meta/
│   │   ├── instructions.md          # Operational rules for AI agents
│   │   ├── index.md                 # Slim hub → sub-indexes
│   │   ├── methods-index.md         # Index of methodology pages
│   │   ├── projects-index.md        # Index of project pages
│   │   ├── vault-map.md             # Static directory map (never goes stale)
│   │   └── changelog.md             # Append-only edit log
│   ├── wiki/
│   │   ├── projects/                # Thin routing pages
│   │   ├── methods/                 # Standalone methodology (project-agnostic)
│   │   ├── decisions/               # Decision graves (why choices were made)
│   │   ├── people/                  # Collaborator context
│   │   └── tools/                   # Environment & tool knowledge
│   └── sources/                     # Read-only raw materials
├── Research/                        # Your raw notes (untouched)
│   ├── Meetings/                    # Meeting notes
│   └── Projects/                    # Project-specific notes
└── Templates/                       # Obsidian templates
```

## How It Works

### Automatic Vault Check (No Trigger Needed)

When you ask about research, methodology, or anything in your vault, Claude automatically:
1. Reads the vault map to find relevant folders
2. Greps those folders for the topic
3. Reads the most recent matching files
4. Answers from your notes, citing file paths

### The Vault Map

A static directory listing — no file counts, no dates. It only breaks when you add a new *folder*, not when you add files. Claude uses Glob/Grep to find specific files within the described folders.

### Source Routing

When you ask about discussions, debates, or advisor opinions, Claude goes to raw meeting notes — not the wiki summary. The wiki is for status; the meetings are for what happened.

### Layered Knowledge

| Layer | Purpose | Example |
|---|---|---|
| **Methods** | Project-agnostic methodology | "What is DiD?" |
| **Projects** | Thin routing pages | "What's the status of my paper?" |
| **Decisions** | Why choices were made | "Why did we switch estimators?" |
| **People** | Collaborator context | "What does my advisor care about?" |
| **Tools** | Environment knowledge | "How do I run OCR?" |

## Quick Start

1. **Copy the template** into your Obsidian vault
2. **Run the setup prompt** (see below) to customize for your workflow
3. **Add your notes** to the raw folders (`Research/`, `Academics/`, etc.)
4. **Start asking Claude** — it will find your notes automatically

## Files Included

| File | Purpose |
|---|---|
| `CLAUDE.md` | Auto-loaded by Claude Code every session |
| `instructions.md` | Full operational rules for AI agents |
| `vault-map.md` | Static directory of your vault |
| `index.md` | Hub linking to sub-indexes |
| `methods-index.md` | Index of methodology pages |
| `projects-index.md` | Index of project pages |
| `changelog.md` | Append-only edit log |
| `Templates/` | Obsidian templates for wiki pages and meetings |

## The Prompt

Use the included prompt (`setup-prompt.md`) to customize this structure for your own workflow. It asks about your:
- Research area and projects
- Advisors and collaborators
- Courses and methodology interests
- Preferred note-taking style
- Folder structure

Then generates a fully customized second brain.

## Requirements

- **Obsidian** (any version)
- **Claude Code** (CLI, desktop, or web)
- **Omnisearch** plugin (optional, for full-text search in Obsidian)

## No RAG Required

This system works without any vector store, embedding pipeline, or RAG infrastructure. The vault map + file search is sufficient for vaults under ~500 files. For larger vaults, consider adding Omnisearch or a local embedding pipeline.

## License

MIT
