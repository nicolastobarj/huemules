# Mutual Los Huemules: blog + second brain

This repo serves two purposes:

1. **Quarto website** (Spanish sociology blog, "Hacia una vía chilena al metamodernismo"), rendered to `docs/`.
2. **Obsidian vault** (the repo root is the vault), where the user writes notes and drafts with friends.

## The user organizes the vault

The user is building the vault's folder structure themselves, over time. Do not create, rename or reorganize folders unless asked. When a note needs saving and the right place is not obvious, ask.

## Notes never leak into the site

`_quarto.yml` renders only `*.qmd` files, so Obsidian `.md` notes can live anywhere without becoming web pages. Keep notes as `.md`. Do not save notes inside the site folders: `docs/` (build output, never edit by hand), `product/`, `images/`, `styles/`, `_includes/`, `workflows/`.

## Note conventions

- Notes in Spanish by default; direct quotes stay in their original language.
- Link notes with `[[wikilinks]]`; search for an existing note before creating one that might duplicate it.
- Never invent quotes, page numbers, dates or bibliographic data. If unsure, write `[verificar]`.
- Keep the author's claim, our paraphrase and our own interpretation visibly separate.
- Obsidian syntax reference: the `obsidian-markdown`, `obsidian-bases`, `json-canvas` skills.

## Site post format (for later)

Posts live in `product/*.qmd` and appear in the `escritos.qmd` listing. Front matter used by existing posts: `title`, `subtitle`, `author`, `date` (MM-DD-YYYY), `image: ../images/<file>`, `css: ["../styles/retro.css"]`, `lang: es`.
