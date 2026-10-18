---
name: capture
description: Quickly capture an idea, quote, observation, link or conversation fragment into the vault inbox (_inbox/) without processing it. Use when the user says "anota", "capture", "save this idea", "jot down", pastes a loose thought or link to keep for later, or asks to save insights from the current conversation.
---

# Capture

Get the thought into the vault fast. Processing happens later with `connect`.

## Steps

1. Pick a short descriptive title (3-7 words, Spanish unless the user writes otherwise). File: `_inbox/<YYYY-MM-DD> <título>.md`.
2. Write the note:

```markdown
---
tipo: captura
creado: YYYY-MM-DD
tags: [inbox]
origen: <conversación | lectura | conversación con X | url>
---

<the idea in the user's own words; keep their phrasing, fix only typos>

## Posibles vínculos
- [[...]]  <!-- existing notes this may relate to -->
```

3. For "Posibles vínculos", run a quick search (Grep over `_conceptos/`, `_autores/`, `_fuentes/`, `_borradores/`) for 2-4 key terms and link only notes that actually exist. If none exist, omit the section.
4. If the capture is a URL, store the URL in `origen` and add one line saying what it is. Do not fetch and summarize it; that is `ingest`.
5. When capturing from the current conversation, write one capture per distinct idea, not one long dump.
6. Reply with the file path(s) only, plus a one-line hint if the idea clearly belongs to an existing draft.

Do not rewrite the user's idea into polished prose. The inbox keeps raw thinking.
