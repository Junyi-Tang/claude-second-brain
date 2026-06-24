---
type: reference
created: "YYYY-MM-DD"
modified: "YYYY-MM-DD"
description: "Dynamic index powered by Dataview — auto-generates from frontmatter"
tags:
  - ai-workspace
  - meta
---
# Dynamic Index (Dataview)

> [!abstract] This page auto-generates
> Lists below update automatically when you add pages with the right frontmatter. No manual maintenance needed for your human-facing view.
> For Claude Code's discovery layer, see [[index]] (static, manually maintained).

---

## Methods Pages

```dataview
TABLE description, modified
FROM "AI_Workspace/wiki/methods"
SORT modified DESC
```

## Project Pages

```dataview
TABLE description, modified
FROM "AI_Workspace/wiki/projects"
SORT modified DESC
```

## Decision Logs

```dataview
TABLE description, modified
FROM "AI_Workspace/wiki/decisions"
SORT modified DESC
```

## People Pages

```dataview
TABLE description, modified
FROM "AI_Workspace/wiki/people"
SORT modified DESC
```

## Tools Pages

```dataview
TABLE description, modified
FROM "AI_Workspace/wiki/tools"
SORT modified DESC
```

## Recent Changes (Last 7 Days)

```dataview
TABLE description, modified
FROM "AI_Workspace/wiki"
WHERE modified >= date(today) - dur(7 days)
SORT modified DESC
```
