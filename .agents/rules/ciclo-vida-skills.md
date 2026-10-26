# Ciclo de vida de skills: estándar → proyecto → estándar

Cómo una skill genérica de BiblioSkills se instala en cualquier proyecto y cómo
las mejoras de un proyecto regresan al estándar como versiones actualizables.

## 1. Formato estándar (lo que vive en BiblioSkills)

Cada skill es `skill/<tema>/<nombre>/` con:

- `SKILL.md` con frontmatter obligatorio + tabla **Variables del proyecto** (ver `skill/plantilla-skill/`).
- `CHANGELOG.md` propio con entradas por versión (semver: `MAYOR.MENOR.PARCHE`).
- Frontmatter mínimo: `name`, `version`, `description` (una línea: cuándo se activa).

```yaml
---
name: mi-skill
version: 1.2.0
description: Qué hace y cuándo usarla.
---
```

Nada de valores concretos de un proyecto dentro de la estándar: solo variables
(`{{paquete_app}}`, `{{ruta_apk}}`, …) con ejemplo en la tabla. Si una skill
todavía trae nombres de un proyecto origen, no es estándar aún: hay que
parametrizarla antes de versionarla como `1.0.0`.

## 2. Instalación en un proyecto (lo que hace el agente)

1. **Mapear**: `codegraph explore` + entrypoints + stack + rutas reales del
   proyecto. Snapshot en `.agents/architecture.md` del proyecto (o en su
   `.agents/input.md` si no existe).
2. **Planear**: plan de integración en el `.agents/input.md` o `tasks.md` del
   proyecto: qué variables instanciar con qué valores, qué choca, y qué debe
   cambiar — la skill, el proyecto, o nada.
3. **Adaptar sin contaminar**: copiar la skill a
   `<proyecto>/.agents/skill/<nombre>/` (o `skills/` según su convención).
   Todo lo específico del proyecto va en un `ADAPTER.md` junto a la copia
   (valores de variables, overrides, scripts). La copia de `SKILL.md` **no se
   edita** salvo fix urgente bloqueante.
4. **Registrar**: anotar `skill <nombre> vX.Y.Z + ADAPTER` y la fecha en las
   tasks/decisiones del proyecto.

## 3. Evolución (proyecto → estándar → resto de proyectos)

1. **Detectar**: una mejora nace en un proyecto. El agente separa lo
   **genérico** (sirve a cualquiera → va al estándar) de lo **específico**
   (se queda en el `ADAPTER.md` de ese proyecto).
2. **Proponer**: cambio a BiblioSkills con bump de versión + entrada en el
   `CHANGELOG.md` de la skill indicando origen (`traída de <proyecto>`).
   - `PARCHE`: fix compatible. `MENOR`: capacidad nueva compatible.
   - `MAYOR`: cambia variables o rompe adaptadores existentes.
3. **Publicar**: el merge en BiblioSkills es la nueva versión estándar.
4. **Actualizar**: solo en los proyectos que la usan **y la necesitan** (nunca
   forzado): el agente re-sincroniza la copia estándar, re-aplica su
   `ADAPTER.md` y verifica con el workflow de la skill. Si el adaptador choca
   con un cambio `MAYOR`, lo reporta antes de tocar nada.

## Reglas

1. `ADAPTER.md` es local al proyecto: nunca se commitea a BiblioSkills.
2. Un valor de variable debe existir en el proyecto (ver `AGENTS.md`): nunca inventar rutas, paquetes, endpoints ni tablas.
3. CHANGELOG por skill, no global. Cada entrada: versión, fecha, qué cambió y origen.
4. Sin updates forzados entre proyectos: cada proyecto actualiza cuando lo necesita.
5. Scripts `.ps1` de una skill en ASCII puro (sin emojis ni acentos): PowerShell 5.1
   lee UTF-8 sin BOM como ANSI y rompe el parse (`string terminator`). Verificado
   con `ota-android-generic` (17 errores fantasma por emojis en strings).
