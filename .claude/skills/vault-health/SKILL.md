---
name: vault-health
description: Audit the Obsidian vault for broken wikilinks, orphan notes, missing or invalid frontmatter, duplicate/near-duplicate notes, stale inbox items, and notes in the wrong place that would leak into the Quarto site. Use when the user says "revisa la bóveda", "vault health", "limpieza", "lint the notes", or periodically before publishing.
---

# Vault health check

Report first, fix only what the user approves.

## Checks

1. **Site leaks (critical):** any `.md` outside underscore folders (except `README.md`, `CLAUDE.md`), any `.qmd` inside underscore folders, and confirm `_quarto.yml` still has `render: ["*.qmd"]`.
2. **Broken links:** every `[[target]]` / `[[target|alias]]` / `![[target]]` must resolve to a file name (without `.md`) or an `aliases` entry somewhere in the vault. Ignore links inside code blocks.
3. **Orphans:** notes in `_fuentes/`, `_conceptos/`, `_autores/` with no incoming links.
4. **Frontmatter:** each note has `tipo`, `creado`, `tags`; `tipo` matches its folder (see `CLAUDE.md`); `fuente` notes have `autor` and `año`; `borrador` notes have a valid `estado`.
5. **Duplicates:** file names that differ only by accents, case, plural or word order (e.g. `Aceleracion social` vs `Aceleración social`).
6. **Stale inbox:** captures in `_inbox/` older than 14 days.
7. **Unverified data:** count of `[verificar]` markers per note.
8. **Draft pipeline:** drafts by `estado`, and any `publicado` draft whose `publicado_en` file does not exist.

Use Grep/Glob or a short script in the scratchpad directory (not in the repo).

## Report

A short summary line (`N notas · X problemas`) followed by one table per check that has findings: file, problem, proposed fix. Then ask which fixes to apply. For duplicates, propose a merge that keeps the richer note, moves unique content over, and adds the other name to `aliases`; rewrite links pointing to the retired note.
