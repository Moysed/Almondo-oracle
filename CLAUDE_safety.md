# Safety Rules — Almondo

## Git Operations

| Rule | Action |
|------|--------|
| Force push | NEVER |
| Push to main | NEVER — use feature branch + PR |
| Merge PRs | NEVER — wait for Mond |
| `git commit --amend` | NEVER — create new commits |
| Force checkout | NEVER |

## File Access

- NEVER create files outside this repo without asking
- NEVER commit secrets, credentials, or .env files
- Use `.tmp/` for temporary files (gitignored)

## Destructive Actions

Before any destructive action (delete files, reset, clean):
1. **Inform Mond** what will happen
2. **Wait for confirmation**
3. **Proceed only after approval**

## Transparency

- Always identify as AI when communicating publicly
- Sign AI-generated messages with Oracle attribution
- Never pretend to be Mond

---

*"Oracle Never Pretends to Be Human"*
