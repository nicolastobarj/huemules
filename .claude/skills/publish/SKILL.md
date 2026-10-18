---
name: publish
description: Convert a finished Obsidian draft from _borradores/ into a Quarto blog post in product/*.qmd for the Los Huemules site — translate wikilinks, embeds, callouts and footnotes to Quarto, copy images, write the front matter, and preview. Use when the user says "publica", "pasa a Quarto", "publish this draft", "súbelo a la página", or a draft reaches estado listo.
---

# Publish a draft to the Quarto site

## 0. Preconditions

- Draft has `estado: listo` (or `revisión` and the user explicitly says publish). Otherwise stop and say what is missing.
- No unresolved `[verificar]` / `[cita por verificar]` markers. If any remain, list them and ask before continuing.

## 1. Slug and file

Slug: lowercase ASCII from the title, underscores, short (`la_voz_2030` style). Target: `product/<slug>.qmd`. Never overwrite an existing file without asking. `product/por_subir_*.qmd` are placeholders the user may want to replace; ask.

## 2. Front matter (match existing posts, see `product/la_voz_2030.qmd`)

```yaml
---
title: "<titulo>"
subtitle: "<subtitulo>"
author: "<autores, joined with ' y '>"
date: MM-DD-YYYY   # publication date, today unless told otherwise
image: ../images/<cover file>
css: ["../styles/retro.css"]
lang: es
---
```

Ask for a cover image if the draft has none; the grid listing in `escritos.qmd` shows it.

## 3. Convert the body (only the `## Texto` section; drop Material, Esquema, review callouts)

| Obsidian | Quarto |
|---|---|
| `[[Nota]]` / `[[Nota\|texto]]` | Plain text (`Nota` / `texto`). If the note is a published post, link to `<slug>.qmd`. If a source note has a `url`, link to it. |
| `![[imagen.png]]` | Copy the file from `_adjuntos/` to `images/` and write `![](../images/imagen.png){fig-alt="..."}` |
| `![[Otra nota]]` (note embed) | Inline its relevant text or drop it; ask if unsure |
| `> [!note] Título` callouts | `::: {.callout-note title="Título"}` ... `:::` (map note/info/tip/warning/important; idea/question/abstract → callout-note) |
| `==resaltado==` | `[resaltado]{.mark}` |
| `%%comentario%%` | delete |
| Footnotes `[^1]` | keep as-is (Pandoc supports them) |
| `#tags` in prose | delete |

Source citations: if a footnote only holds a wikilink to a `_fuentes/` note, replace it with a readable reference built from that note's frontmatter (`Autor, *Título* (año)`, plus URL if any).

## 4. Check

- Grep the new `.qmd` for leftover `[[`, `![[`, `> [!`, `%%`.
- Run `quarto render product/<slug>.qmd` and report errors. Offer `quarto preview` for the user to look at it.
- Do not commit or push unless asked. Pushing to `main` deploys the site to Netlify.

## 5. Close the loop

Update the draft: `estado: publicado`, `publicado_en: product/<slug>.qmd`.
