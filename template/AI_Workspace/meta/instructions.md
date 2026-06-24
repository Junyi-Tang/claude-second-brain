---
type: reference
created: "YYYY-MM-DD"
modified: "YYYY-MM-DD"
description: "instructions"
tags:
  - ai-workspace
  - meta
---
# Universal AI Agent Operational Schema

**CRITICAL:** Any AI agent entering this workspace must read this file first, and re-read it at the start of any multi-step task. Do not rely on conversational memory. Your state and memory exist entirely within these Markdown files.

This vault is a personal knowledge base. Default to the register and precision of the user's domain unless signaled otherwise.

## 1. Directory Rules

- `/sources`: **READ-ONLY.** You may read files here to extract information. You are strictly forbidden from modifying, deleting, renaming, or moving any file in this directory. If a source appears wrong or outdated, surface the issue to the user — do not edit it.
- `/wiki`: **WRITE-ACCESS.** This is your workshop. Organized into subdirectories:
  - `/wiki/projects/` — thin project routing pages (links to methods, decisions, people, raw notes)
  - `/wiki/methods/` — standalone, project-agnostic methodology knowledge
  - `/wiki/decisions/` — decision graves per project (why choices were made)
  - `/wiki/people/` — collaborator context (advisor preferences, feedback patterns)
  - `/wiki/tools/` — environment and tool knowledge
  - `/wiki/` (root) — legacy pages being migrated to subdirs
- `/meta/index.md`: **WRITE-ACCESS.** This is the master catalog. Every time you create or meaningfully modify a file in `/wiki`, you MUST update this index with a one-line summary and a wiki-link to the file.
- `/meta/vault-map.md`: **WRITE-ACCESS.** Static directory map (no file counts or dates — use Glob/Grep to discover files). Only update when a new folder is created or a folder's purpose changes.
- `/meta/`: Other files in this directory are intentional hubs and must not be flagged as orphans during linting.
- **Full vault query path:** All user folders outside `AI_Workspace/` are **READ-ACCESS** for queries. The user's raw notes live there. Do not modify them.

## 2. File Naming & Linking Conventions

- Filenames use **kebab-case with full words**, no abbreviations unless the abbreviation is the canonical name.
- Before creating a new page, search `index.md` and `/wiki` for existing pages on the same concept under alternate names. Prefer updating over duplicating.
- All internal references use Obsidian wiki-links: `[[filename]]`. Never use standard Markdown links for intra-vault references.
- When a wiki-link points to a page that does not yet exist, either create a stub page for it in the same operation or note the missing page in your response.

## 3. The Operational Loop

Identify which operation the user's request maps to before acting.

### INGESTION

When the user adds a file to `/sources` or provides new information:

1. Cross-reference against `index.md` to identify what already exists on the topic.
2. Decide whether the information warrants a new page, updates to existing pages, both, or neither. **You have explicit permission to conclude that a source is redundant or low-signal and requires no vault changes** — say so rather than manufacturing edits.
3. Update related existing pages **only where the new information genuinely changes, extends, or qualifies them.**
4. When new information contradicts an existing claim, **do not overwrite silently.** Preserve the prior claim, add the new one, and mark the conflict with an Obsidian callout:
```
   > [!conflict] Contradicts prior claim
   > Previous: [summary of old claim, with source]
   > New: [summary of new claim, with source]
```
5. When you infer something beyond what the source explicitly states, tag the claim with `#inferred` so it can be reviewed during linting.
6. Update `index.md` with entries for any new or meaningfully changed pages.

### QUERY

When the user asks a question:

1. Read `/meta/vault-map.md` first to identify which folders are relevant.
2. Read `/meta/index.md` to locate relevant wiki pages (curated knowledge layer).
3. For research questions: check `/wiki/` (curated) first, then raw notes, then course materials. The wiki is the distilled knowledge; raw notes provide detail and context.
4. **Recency rule:** when multiple files cover the same topic, read the most recent first (check file modification dates or dates in filenames). Earlier files provide context only if the latest is ambiguous.
5. For meeting-related questions: read from latest backward.
6. For methodology questions: `/wiki/methods/` has standalone explanations. Course notes may have additional depth.
7. Construct the answer and cite sources using wiki-links: `[[filename]]` for wiki pages, or file paths for raw notes.
8. If the vault contains no relevant material, say so — do not fabricate.
9. If pages disagree, present both positions and note the disagreement rather than picking one silently.

### LINTING

When the user asks you to "lint" or "maintain" the vault:

1. Scan `/wiki` for: contradictions, orphaned pages (no inbound or outbound links, excluding `/meta/` hubs), broken wiki-links, duplicate pages under different names, and `#inferred` claims that need review.
2. Produce a report of everything found.
3. **Apply only the mechanical fixes yourself:** repairing broken links where the target is unambiguous, merging obvious duplicates, adding links from clearly related orphans.
4. **Flag substantive issues for user review:** contradictions, stale claims, ambiguous duplicates, and `#inferred` claims. Do not resolve these unilaterally.

### NOTE

When the user says "note this" or "log this":

1. Write a short (1-3 paragraph) entry to the most relevant wiki page, appending it under a dated heading.
2. If no relevant page exists, create a stub in the appropriate `/wiki/` subdirectory.
3. If the note relates to a decision, add it to the relevant `/wiki/decisions/` page.
4. If the note relates to a collaborator interaction, add it to the relevant `/wiki/people/` page.
5. Update `index.md` if a new page was created.

## 4. Formatting & Style

- Favor dense, structured Markdown: headers, bullet points, code blocks, tables where they earn their place.
- Preserve mathematical notation and code snippets verbatim from sources. Do not paraphrase equations.
- Build a cohesive web: a new technical concept should link to the project it belongs to, the tools used to implement it, the underlying theory, and any related methods it's compared or contrasted with.
- Every page should have at least one outbound link. A page with no links is a signal you haven't finished thinking about where it belongs.
