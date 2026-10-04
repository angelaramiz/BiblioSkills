# AGENTS.md — BiblioSkills

Repo greenfield: biblioteca de agent-skills reutilizables (solo Markdown). Sin build, test, lint ni deploy — nada que ejecutar. Patrón de referencia: `C:\Users\angel\Desktop\CalendarFinace\.agents\skill\agents-architecture` (`SKILL.md`, 121 líneas).

## Estructura prevista

- `skill/<nombre-skill>/SKILL.md` — un directorio por skill, doc + scripts/assets junto a ella.
- `.agents/tasks.md` — tareas activas; `.agents/input.md` — instrucciones pendientes; `.agents/rules/`, `.agents/roles/`, `.agents/meetings/decisions/`, `.agents/history/` — solo si se crean.
- Índice `.codegraph/` (si se inicializa): nunca commitear `*.db*`, `daemon.pid`, `daemon.log`.

## Añadir una skill

- Seguir la forma del `SKILL.md` de referencia: Resumen → Estructura → Componentes → Flujo de trabajo → Instalación/uso → Referencias. Prosa en español.
- Una capacidad por skill; promover un workflow a skill solo si se repite entre sesiones y sus reglas ya son estables.
- Preferir verdad ejecutable: comandos, rutas y nombres de tablas/endpoints deben existir en código/config — nunca inventar URLs, paquetes ni tablas.

## Ciclo de vida (resumen)

- Formato estándar: frontmatter `name/version/description` + tabla Variables del proyecto + `CHANGELOG.md` por skill. Plantilla: `skill/plantilla-skill/`.
- Instalación: mapear proyecto → plan en su `.agents/input.md` → copiar a `<proyecto>/.agents/skill/<nombre>/` + `ADAPTER.md` local (la copia estándar no se edita).
- Evolución: mejora en proyecto → separar genérico/específico → bump semver + changelog → otros proyectos re-sincronizan solo si lo necesitan.
- Detalle: `.agents/rules/ciclo-vida-skills.md`.

## Flujo del agente

1. Leer `AGENTS.md`, luego `.agents/input.md` + `.agents/tasks.md` si existen.
2. `codegraph explore "<query>"` antes de grep/find en código indexado.
3. Actualizar tareas/decisiones tras el trabajo; ediciones mínimas y en el estilo existente.

## Reglas

1. Responde SIEMPRE en español: toda la conversación, explicaciones y respuestas al usuario van en español.
