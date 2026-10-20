---
name: connect
description: Find connections across the vault's notes — what the notes say about a topic, how different authors agree or clash, recurring themes in recent notes, links between two ideas, and loose captures that belong together. Use when the user says "conecta", "relaciona A con B", "qué dicen mis notas sobre X", "qué temas se repiten", "synthesize", or wants ideas for what to write next.
---

# Connect and synthesize

Search the whole vault (all `.md` files except the site folders listed in `CLAUDE.md`). Do not assume any folder structure.

## Modes (pick from the request)

- **Topic ("qué dicen mis notas sobre X"):** gather the notes that mention X or related terms (follow `[[links]]` one hop). Answer with: positions (by author or note), agreements, tensions, gaps the vault does not cover yet, and ideas for essays.
- **Emerge ("qué temas se repiten"):** read notes created or changed in the last ~30 days (file dates or `git log`) and report 3-5 recurring themes, with the notes behind each one.
- **Bridge ("relaciona A con B"):** find what links two notes or topics and lay out the argument connecting them, with evidence from each side.
- **Loose notes:** find notes with no links, or captures that repeat the same idea, and propose which to link or merge.

## Rules

- Every claim must point to a vault note with `[[...]]`. Mark your own inferences as such. If you add knowledge from outside the vault, label it "fuera de la bóveda" so the user can verify it.
- Answer in the chat by default. Save the result as a note only if the user asks, and ask where.
- Propose changes to existing notes (adding links, merging) and apply them only once the user approves. Never delete content without confirmation.
