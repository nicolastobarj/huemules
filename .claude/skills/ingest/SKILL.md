---
name: ingest
description: Turn a source (URL, PDF, book chapter, interview, YouTube/podcast transcript, pasted text) into a faithful reading note in the vault, linked to existing notes on the same authors and concepts. Use when the user shares a reading, says "fichar", "fichaje", "ingest", "resume este texto para la bóveda", or wants reading notes on sociology or theory material.
---

# Ingest a source

Goal: one faithful reading note, linked to the rest of the vault. Accuracy over coverage.

## 1. Get the text

- Web page: use the `defuddle` skill; if it fails, use WebFetch.
- PDF: use the `pdf` skill or Read with `pages`. For a long book, ask which chapters.
- Pasted text or transcript: use it as-is.
- If you only got part of it (paywall, abstract only), say so in the note. Never fill gaps from memory as if they came from the source.

## 2. Where to save

Do not create folders on your own. If an existing folder is clearly for readings or sources, use it; otherwise ask once (suggest the root). Before writing, search the vault for notes that already exist on the same work, author or concepts, and reuse or link to them instead of duplicating.

## 3. The note

Name: `<Apellido> <Año> - <Título corto>.md`. Write in Spanish unless the user writes otherwise; quotes stay in their original language.

```markdown
---
autor: "<Nombre Apellido>"
titulo: "<título completo>"
año: <año>
url: <si aplica>
creado: YYYY-MM-DD
---

> [!abstract] En una frase
> <the core argument>

## Argumento central
<short paraphrase, following the source's order>

## Citas clave
> "<exact quote>" (p. X)

## Conceptos
- <concept>: how the source defines or uses it

> [!idea] Ideas propias
> <only interpretations the user stated, or suggestions clearly marked as such>

## Preguntas abiertas
```

- Link with `[[...]]` only to notes that exist. Do not create author or concept notes unless the user asks.
- Quotes verbatim, only from the text actually read; page numbers only if the source shows them; `[verificar]` for anything uncertain.

## 4. Report

Say which note was created, which existing notes it links to, and anything marked `[verificar]` or read only in part.
