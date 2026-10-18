---
name: weekly-review
description: Run a weekly or monthly review of the vault and blog work — what was read, captured and written, where each draft stands, what is stuck, and the next concrete steps. Use when the user says "revisión semanal", "weekly review", "¿en qué quedé?", "resume la semana", or starts a session wanting to know where things stand.
---

# Weekly review

## Gather

- Period: last 7 days by default (or what the user says).
- `git log --since="<period>" --name-status` for files added/changed, plus uncommitted changes from `git status`.
- New or updated notes per folder; drafts and their `estado`; inbox size and oldest item.

## Write

File: `_mapas/Revisión <YYYY>-W<semana>.md` (`tipo: mapa`, `tags: [revision]`):

```markdown
## Leído y fichado
- [[fuente]]: one line

## Ideas nuevas
- [[captura o concepto]]

## Borradores
| Borrador | Estado | Avance esta semana | Siguiente paso |

## Atascado
- <drafts untouched > 2 weeks, inbox backlog, `[verificar]` pending>

## Próxima semana
1. <max 3 concrete actions, e.g. "fichar capítulo 3 de Rosa para el borrador X">
```

Keep it short. Then ask the user two questions: what they want to prioritize, and whether anything should be dropped. Record their answers under `## Decisiones`.

Offer to commit the week's notes (do not push unless asked).
