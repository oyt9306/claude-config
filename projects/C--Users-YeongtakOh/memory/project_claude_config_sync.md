---
name: claude-config GitHub sync workflow
description: How to sync ~/.claude config (skills, CLAUDE.md, plugins) to GitHub
type: project
---

User syncs ~/.claude to GitHub repo (oyt9306/claude-config) as a cross-machine config backup.

**Why:** New machine setup requires cloning this repo to get all skills, CLAUDE.md, and plugin configs restored automatically.

**How to apply:** When user wants to push config changes, follow this workflow:
1. `cd ~/.claude && git add` specific files (skills/, plugins/, CLAUDE.md, .gitignore, etc.)
2. Exclude machine-specific items: `agent-memory/`, `mcp-needs-auth-cache.json`, `skills/notebooklm/` (nested git repo with per-machine auth)
3. Commit and push to main

**Key .gitignore rules:**
- `agent-memory/` — local agent memory, machine-specific
- `mcp-needs-auth-cache.json` — auth cache, machine-specific
- `skills/notebooklm/` — nested git repo, re-auth required per machine
- `plugins/cache/`, `plugins/marketplaces/` — re-downloadable

**New machine setup:**
```bash
git clone https://github.com/oyt9306/claude-config.git ~/.claude
/plugin install superpowers@claude-plugins-official
/plugin install document-skills@anthropic-agent-skills
/plugin install example-skills@anthropic-agent-skills
/plugin install claude-mem@thedotmack
cd ~/.claude/skills/notebooklm && python scripts/run.py auth_manager.py setup
```
