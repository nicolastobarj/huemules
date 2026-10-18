---
name: connect
description: Process the inbox and find connections across the vault — link captures to concepts, surface recurring themes, compare what different authors say about a topic, and write synthesis or map-of-content notes in _mapas/. Use when the user says "procesa el inbox", "conecta", "synthesize", "what do my notes say about X", "qué temas se repiten", "relaciona A con B", or wants ideas for what to write next.
---

# Connect and synthesize

Three modes. Pick from the request; if unclear, run **inbox** then offer **emerge**.

## Mode: inbox (process `_inbox/`)

For each capture, oldest first:
1. Read it and search the vault for related notes.
2. Propose one action: **merge** into an existing concept/draft note (append with link back), **promote** to a new `_conceptos/` note, **feed** a draft in `_borradores/` (add under its `## Material` section), or **keep** (still raw).
3. Show the plan as a table (capture → action → target) and ask before applying. Then apply: move promoted/merged captures out of `_inbox/` by deleting them only after their content lives elsewhere, with a backlink in the target (`Origen: captura del YYYY-MM-DD`).

## Mode: topic synthesis ("qué dicen mis notas sobre X")

1. Gather every note that mentions X or its aliases (Grep on body and frontmatter; follow wikilinks one hop).
2. Write `_mapas/Síntesis - <X>.md` (`tipo: mapa`) with sections: **Posiciones** (per author, linked, with citations from the notes), **Acuerdos**, **Tensiones y contradicciones**, **Vacíos** (what the vault does not cover yet), **Ideas para escritos**.
3. Every claim must trace to a vault note via wikilink. Mark your own inferences with `> [!idea]`. Do not import outside knowledge silently; if you add context the vault lacks, label it `> [!info] Fuera de la bóveda` so the user can verify it.

## Mode: emerge / bridge

- **Emerge:** read notes created or modified in the last ~30 days (use `git log --since` or file mtimes) and report 3-5 recurring themes, with the notes that carry each one, and which could become an essay.
- **Bridge A↔B:** given two notes or domains (e.g. "Jorge González" and "resonancia"), find shared concepts, write `_mapas/Puente - <A> y <B>.md` with the argument linking them and the evidence from each side.

## Maps of content

When a concept or author accumulates 5+ linked notes, offer to create or update `_mapas/MOC - <tema>.md`: a curated, grouped list of links with one line each. For a visual version, use the `json-canvas` skill to write `_mapas/<tema>.canvas`.

Never delete user-written content without confirmation.
