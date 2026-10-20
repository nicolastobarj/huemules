---
name: capture
description: Quickly capture an idea, quote, observation, link or conversation fragment as a note in the vault without processing it. Use when the user says "anota", "capture", "guarda esta idea", "jot down", pastes a loose thought or link to keep for later, or asks to save insights from the current conversation.
---

# Capture

Get the thought into the vault fast. Organizing it comes later (`connect`).

## Where to save

The user is building the folder structure themselves. Do not create folders on your own.
1. Look at the existing folders (excluding the site folders listed in `CLAUDE.md`). If one is clearly meant for captures or loose ideas, use it.
2. Otherwise ask once where to save captures, and suggest the vault root as the default. Follow that answer for the rest of the session.

## The note

File name: `<YYYY-MM-DD> <título breve>.md` (3-7 words, in the user's language).

```markdown
---
creado: YYYY-MM-DD
origen: <conversación | lectura | url | ...>
---

<the idea in the user's own words; fix only typos>

Relacionado: [[...]]
```

- For `Relacionado`, search the vault for 2-4 key terms and link only notes that actually exist. Omit the line if there are none.
- If it is a URL, put it in `origen` with one line on what it is. Do not fetch or summarize it; that is `ingest`.
- From a conversation: one note per distinct idea, not a single dump.
- Do not rewrite the idea into polished prose.

Reply with the path(s) of the notes created.
