# Second Brain Setup Prompt

> Copy the prompt below and paste it into Claude Code. It will guide you through setting up a fully customized second brain in your Obsidian vault.

---

```
I want to set up a "second brain" in my Obsidian vault that Claude Code can automatically search and use. I have the Claude Second Brain template files. Please guide me through the setup by asking me the following questions, then configure everything for me.

## Questions to Ask Me

Ask these one at a time. Wait for my answer before moving to the next.

### 1. Vault Location
- Where is your Obsidian vault? (full path)
- What are the main top-level folders in your vault? (e.g., Research/, Academics/, Projects/, Personal/)

### 2. Research & Projects
- What is your primary research area or main focus?
- What active projects do you have? For each:
  - Project name
  - One-line description
  - Deadline (if any)
  - Key methods used
- What deferred or completed projects should be tracked?

### 3. Collaborators & People
- Who are your key collaborators? For each:
  - Name
  - Role (advisor, co-author, mentor, etc.)
  - What they care about methodologically
  - Their communication style
- Are there specific feedback patterns you want to remember?

### 4. Methodology & Knowledge
- What methods do you use regularly? (e.g., DiD, IV, GMM, ML, specific statistical methods)
- What methods have you learned in courses that might be useful later?
- Are there methodology debates or preferences in your field?

### 5. Meeting & Decision Tracking
- How often do you have research meetings? (weekly, biweekly, etc.)
- What format do your meeting notes follow?
- Do you want to track decisions with reasoning? (recommended)
- What types of decisions are common in your work?

### 6. Tools & Environment
- What programming languages/tools do you use? (Python, R, Stata, etc.)
- Are there any known issues or workarounds in your environment?
- Do you have any custom scripts or tools?

### 7. Query Preferences
- When you ask a question, do you prefer:
  - Answers from curated wiki pages first (status/summary)?
  - Answers from raw notes first (detailed/verbatim)?
  - Both, with the source clearly labeled?
- What domains should trigger automatic vault search? (e.g., research, methodology, course material, meeting notes)

### 8. Obsidian Setup
- Do you have the Omnisearch plugin installed? (recommended)
- Do you use Obsidian Copilot? If so, what embedding model?
- Do you have daily notes enabled?
- What templates do you already have?

## After My Answers

Based on my answers, please:

1. **Update CLAUDE.md** with:
   - My vault path
   - My user profile (role, background, focus)
   - My domain-specific trigger keywords
   - My query preferences

2. **Update vault-map.md** with:
   - My actual folder structure and descriptions
   - Source routing rules based on my preferences

3. **Update index.md** with:
   - Initial entries for my active projects
   - Initial entries for my collaborators
   - Initial entries for my tools

4. **Create starter pages** for:
   - Each active project (thin routing page in wiki/projects/)
   - Each collaborator (in wiki/people/)
   - Key methods I use (in wiki/methods/)

5. **Update instructions.md** if my workflow has special needs

6. **Verify** everything works by:
   - Checking all wiki-links resolve
   - Testing a sample query path
   - Confirming the vault map covers all my folders

## File Locations

The template files should be at:
- `[VAULT]/AI_Workspace/meta/instructions.md`
- `[VAULT]/AI_Workspace/meta/vault-map.md`
- `[VAULT]/AI_Workspace/meta/index.md`
- `[VAULT]/AI_Workspace/meta/methods-index.md`
- `[VAULT]/AI_Workspace/meta/projects-index.md`
- `[VAULT]/AI_Workspace/meta/changelog.md`
- `[VAULT]/CLAUDE.md`
- `[VAULT]/Templates/Wiki Page.md`
- `[VAULT]/Templates/Meeting Note.md`

## Important Notes

- Do NOT modify my existing notes or folders. Only create/update files in AI_Workspace/ and Templates/.
- Keep my existing folder names and structure. Work with what I have.
- If I already have some of these files, update them rather than overwriting.
- The goal is a working second brain, not a perfect one. I can refine it over time.
```

---

## What This Does

The prompt will:

1. **Ask you 8 categories of questions** about your workflow, projects, collaborators, and preferences
2. **Generate a fully customized second brain** with:
   - Your vault paths and folder structure
   - Your projects, people, and methods pre-populated
   - Your query preferences configured
   - Starter pages ready to use
3. **Verify everything works** by checking links and testing queries

## After Setup

Once configured, you can:

- **Ask questions naturally** — Claude checks your vault automatically
- **Say "note this"** — to log something to your wiki
- **Say "ingest"** — to create new wiki pages from information
- **Say "lint vault"** — to check for issues
- **Add notes daily** — no index updates needed for raw notes
- **Create wiki pages** — when you want to curate knowledge

The system grows with you. Add notes, create pages, and the second brain gets smarter over time.
