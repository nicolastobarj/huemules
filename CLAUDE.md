# Mutual Los Huemules: blog + second brain

This repo serves two purposes:

1. **Quarto website** (Spanish sociology blog, "Hacia una vía chilena al metamodernismo"), rendered to `docs/` and deployed to Netlify by `workflows/publish.yml` on push to `main`.
2. **Obsidian vault** (the repo root is the vault). Notes are drafted here and later published as site pages.

## Hard rule: notes never leak into the site

`_quarto.yml` renders only `*.qmd` files. Obsidian notes are `.md` and must live in the underscore folders below (Quarto also ignores anything starting with `_` or `.`). Never create a `.md` note at the repo root or inside `product/`, `images/`, `styles/`, `docs/`. Never hand-edit `docs/`; it is build output.

## Vault layout

| Folder | Contents | `tipo` |
|---|---|---|
| `_inbox/` | Quick, unprocessed captures | `captura` |
| `_fuentes/` | One note per source read: book, article, interview, video, podcast | `fuente` |
| `_autores/` | One note per thinker (Hartmut Rosa, Luhmann, ...) | `autor` |
| `_conceptos/` | One atomic note per concept (aceleración social, resonancia, ...) | `concepto` |
| `_mapas/` | Maps of content, syntheses, `.canvas` maps | `mapa` |
| `_borradores/` | Essays in progress for the blog | `borrador` |
| `_plantillas/` | Note templates for manual use in Obsidian | (none) |
| `_adjuntos/` | Images and PDFs embedded in notes | (none) |

## Note conventions

- **Language:** notes are written in Spanish by default (the blog is Spanish). Direct quotes stay in their original language. Follow the user if they write a note in another language.
- **File names:** human-readable titles with accents allowed, e.g. `Aceleración social.md`, `Hartmut Rosa.md`. Source notes: `Apellido Año - Título corto.md`, e.g. `Rosa 2016 - Resonancia.md`.
- **Links:** use `[[wikilinks]]` between notes. Every `fuente` links its `autor` and the `concepto` notes it develops; every `concepto` links back to the sources that ground it. Prefer linking to an existing note over creating a near-duplicate; search first.
- **Properties (YAML frontmatter):** every note has `tipo`, `creado` (YYYY-MM-DD) and `tags`. Type-specific fields are in the templates under `_plantillas/` and in each skill.
- **Citations:** keep page numbers when known, as `(Rosa 2016, p. 42)`. Never invent quotes, page numbers, dates or bibliographic data. If unknown, write `[verificar]`.
- **Distinguish voices:** an author's claim, our paraphrase, and our own interpretation must be visibly different (quote block, plain text, and a `> [!idea]` callout respectively).
- Obsidian syntax reference: the `obsidian-markdown`, `obsidian-bases`, `json-canvas` skills.

## Draft lifecycle

`estado` in `_borradores/`: `idea` → `esquema` → `borrador` → `revisión` → `listo` → `publicado`.
Publishing converts a `listo` draft into `product/<slug>.qmd` (see the `publish` skill), copies images to `images/`, and sets the draft to `publicado` with `publicado_en: product/<slug>.qmd`.

## Site post format

Posts live in `product/*.qmd` and appear in the `escritos.qmd` grid listing. Front matter used by existing posts:

```yaml
title: "..."
subtitle: "..."
author: "Nombre Apellido"
date: MM-DD-YYYY
image: ../images/<file>
css: ["../styles/retro.css"]
lang: es
```

Preview locally with `quarto preview`; build with `quarto render`.
