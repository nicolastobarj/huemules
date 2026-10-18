---
name: draft
description: Start or develop a blog essay in _borradores/ from vault notes — create the draft note, build an outline from sources and concepts, expand sections, keep the author's voice, and track its estado (idea → esquema → borrador → revisión → listo). Use when the user says "quiero escribir sobre", "nuevo borrador", "start a draft", "arma un esquema", "desarrolla esta sección", or asks for help writing a post for Los Huemules.
---

# Draft an essay

The user and their friends are the authors. Claude organizes material, proposes structure and helps write, but the argument and voice are theirs.

## New draft

File: `_borradores/<Título provisional>.md`

```markdown
---
tipo: borrador
creado: YYYY-MM-DD
tags: [borrador]
estado: idea
titulo: "<título provisional>"
subtitulo: ""
autores: ["<nombre de quien escribe>"]
fuentes: []
publicado_en: ""
---

# <Título>

> [!question] Tesis
> <one sentence: what this essay argues. Ask the user if unclear.>

## Material
<links to captures, sources, concepts gathered for this essay>

## Esquema

## Texto
```

Before writing anything, ask (once, briefly) for the thesis and who signs it, unless already stated.

## Outline (`estado: esquema`)

1. Search the vault for notes related to the thesis; list them under `## Material` with one line on how each serves the argument.
2. Propose an outline of 4-7 sections: hook, problem, argument steps, counterpoint, closing. Under each heading, list which notes/quotes support it.
3. Point out gaps: claims in the outline that no vault note supports yet (suggest `ingest` for them).

## Writing sections (`estado: borrador`)

- Write in Spanish, essayistic register suited to a public sociology blog: clear, argued, with a personal edge; no academic boilerplate, no bullet lists in the prose.
- When the user has written any prose, match their tone, sentence length and Chilean idiom rather than imposing a style.
- Cite with author-year inline (`Rosa (2016)`) and keep the `[[link]]` to the source note in a footnote or in `## Material` so publishing can resolve it.
- Only quote what is in a vault source note; otherwise mark `[cita por verificar]`.
- Expand one section at a time when asked; do not rewrite sections the user already wrote unless asked.

## Status

Update `estado` as the draft advances. When the user considers it done, suggest running `challenge` (→ `revisión`) and then `publish` (needs `listo`).
