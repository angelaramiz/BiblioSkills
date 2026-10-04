# Decisión 2026-10-04 — Ciclo de vida estándar → proyecto → estándar

## Contexto

Las mismas skills (`agents-architecture`, `ota-android-generic`,
`emulador-android`, `android-kotlin-app`) están duplicadas en varios proyectos
con pequeñas variaciones. BiblioSkills existe para unificarlas.

## Decisión

1. Formato estándar con frontmatter (`name/version/description`), tabla de
   Variables del proyecto y `CHANGELOG.md` por skill.
2. Instalación en 4 pasos: mapear → planear → adaptar (`ADAPTER.md` local,
   sin editar la copia estándar) → registrar versión instalada.
3. Evolución en 4 pasos: detectar → proponer (bump semver + changelog) →
   publicar → actualizar solo donde se necesite.
4. `ADAPTER.md` nunca entra a BiblioSkills; updates entre proyectos nunca forzados.

Detalle: `.agents/rules/ciclo-vida-skills.md`.
