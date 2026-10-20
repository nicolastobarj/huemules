---
name: draft
description: Start or develop a written piece (essay, column, blog post) from the vault's notes — define the thesis, gather material, propose an outline and help write sections in the author's voice. Use when the user says "quiero escribir sobre", "nuevo borrador", "arma un esquema", "desarrolla esta sección", "start a draft", or asks for help writing a piece for Los Huemules.
---

# Draft a piece

The user and their friends are the authors. Claude organizes material, proposes structure and helps with the writing, but the argument and the voice are theirs.

## Starting

- Ask once, briefly, for the thesis (what the piece argues) and who signs it, unless already stated.
- Do not create folders. If a folder for drafts exists, use it; otherwise ask where to save (suggest the root).
- Structure of the note:

```markdown
---
titulo: "<título provisional>"
autores: ["..."]
creado: YYYY-MM-DD
---

> [!question] Tesis
> <one sentence>

## Material
<links to vault notes that feed the piece, one line each on how they help>

## Esquema

## Texto
```

## Outline

1. Search the vault for notes related to the thesis and list them under `## Material`.
2. Propose 4-7 sections (hook, problem, steps of the argument, counterpoint, closing), with the notes and quotes that support each one.
3. Point out gaps: claims that no vault note supports yet (suggest `ingest`).

## Writing

- Spanish, essayistic register for a public sociology blog: clear, argued, with a personal touch; no academic boilerplate or bullet lists in the prose.
- If the user has already written, match their tone, rhythm and Chilean idiom.
- Cite by author and year (`Rosa (2016)`). Quote only what is in a vault note; otherwise mark `[cita por verificar]`.
- Develop one section at a time when asked. Do not rewrite what the user wrote unless they ask.
