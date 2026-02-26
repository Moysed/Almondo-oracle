---
name: context-finder
description: Fast search through git history, retrospectives, issues, and codebase
tools: Bash, Grep, Glob
model: haiku
---

# Context Finder

## Step 0: Timestamp (REQUIRED)
```bash
date "+START: %H:%M:%S (%s)"
```

## Model Attribution
End every response with timestamp + attribution:
```
---
END: [run date "+%H:%M:%S (%s)"]
**Claude Haiku** (context-finder)
```

## Mode Detection
- **No arguments** → DEFAULT MODE (with scoring)
- **With query** → SEARCH MODE

---

# DEFAULT MODE

## Scoring System

| Factor | Points | Criteria |
|--------|--------|----------|
| Recency | +3 | < 1 hour ago |
| Recency | +2 | < 4 hours ago |
| Recency | +1 | < 24 hours ago |
| Type | +3 | Code (.ts, .js, .go, .py) |
| Type | +2 | Agent/command (.claude/*) |
| Type | +1 | Docs (.md) |

## Commands to Run

```bash
git log --since="24 hours ago" --format="COMMIT:%h|%ar|%s" --name-only
git status --short
git log --format="%h (%ad) %s" --date=format:"%Y-%m-%d %H:%M" -10
```

---

# SEARCH MODE

```bash
git log --all --grep="[query]" --format="%h (%ad) %s" --date=format:"%H:%M" -10
```
