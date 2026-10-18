---
name: ingest
description: Turn a source (URL, PDF, book chapter, interview, YouTube/podcast transcript, pasted text) into a structured source note in _fuentes/, and create or update the linked author and concept notes. Use when the user shares a reading, says "fichar", "fichaje", "ingest", "add this source", "resume este texto para la bóveda", or wants literature notes for sociology/theory material.
---

# Ingest a source

Goal: one faithful source note plus updated author and concept notes, all interlinked. Accuracy over coverage.

## 1. Get the text

- Web page: use the `defuddle` skill to extract clean Markdown. If that fails, use WebFetch.
- PDF: use the `pdf` skill or Read with `pages`. For long books, ask which chapters, or process in chunks.
- Pasted text or transcript: use as-is.
- If the full text is not accessible (paywall, abstract only), say so and set `acceso: parcial`. Never fill gaps from memory as if they were in the source.

## 2. Check what already exists

Search `_fuentes/`, `_autores/`, `_conceptos/` (file names and `aliases`) for the author, the work and its 3-6 central concepts. Reuse existing notes; never create `Aceleracion social.md` when `Aceleración social.md` exists.

## 3. Write the source note

File: `_fuentes/<Apellido> <Año> - <Título corto>.md`

```markdown
---
tipo: fuente
creado: YYYY-MM-DD
tags: [fuente, <tema>]
autor: "[[Apellido Nombre]]"
titulo: "<título completo>"
año: <año de publicación original>
formato: <libro | capítulo | artículo | entrevista | video | podcast | web>
url: <si aplica>
acceso: <completo | parcial>
estado: <por leer | leyendo | fichado>
conceptos: ["[[Concepto 1]]", "[[Concepto 2]]"]
---

# <Título>

> [!abstract] En una frase
> <the core argument in one sentence>

## Argumento central
<3-6 short paragraphs in Spanish paraphrasing the line of argument, in order>

## Citas clave
> "<exact quote, original language>" (p. X)

## Conceptos
- [[Concepto]]: <how this source defines or uses it>

## Diálogo con otros autores
- <explicit references the source makes, linked if the author note exists>

> [!idea] Para Los Huemules
> <only if the user stated an interpretation, or clearly marked as a suggestion: relevance for Chile, metamodernism, a possible essay>

## Preguntas abiertas
- ...
```

Rules: quotes are verbatim and only from the text you actually read; page numbers only when the source shows them; `[verificar]` for anything uncertain.

## 4. Author note (`_autores/<Nombre Apellido>.md`)

Create if missing (`tipo: autor`, `tradición`, `nacionalidad`, `aliases`); add a line under `## Obras en la bóveda` linking the new source. Biographical facts only if well established; otherwise leave the field empty.

## 5. Concept notes (`_conceptos/<Concepto>.md`)

For each central concept: create if missing (`tipo: concepto`, `aliases`, `autores`). Add a dated bullet under `## Desarrollos` with the source's definition and a link to the source note. Keep concept notes atomic: one concept, what it means, who uses it, how sources differ.

## 6. Report

List created vs. updated files, and flag anything marked `[verificar]` or `acceso: parcial`.
