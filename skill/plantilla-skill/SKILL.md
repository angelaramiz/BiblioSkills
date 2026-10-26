---
name: plantilla-skill
version: 0.1.0
description: Plantilla de skill estándar. Se activa como ejemplo de formato, no como capacidad real.
---

# SKILL: plantilla-skill

> Plantilla permanente: duplícala como `skill/<tema>/<nombre-skill>/` para crear una
> skill estándar. No borrar este directorio.

## Resumen

2-3 líneas: qué capacidad aporta y cuándo debe usarla el agente.

## Variables del proyecto

Toda skill estándar parametriza lo específico de cada proyecto. Sin valores
reales aquí — solo variables con ejemplo.

| Variable | Descripción | Ejemplo |
|----------|-------------|---------|
| `{{ruta_base}}` | Raíz donde se instala en el proyecto destino | `.agents/skill/mi-skill/` |
| `{{comando_clave}}` | Comando o entrypoint que varía por proyecto | `npm run dev` |

## Uso

Pasos genéricos, con `{{variables}}` donde aplique:

```
1. Instanciar variables (ver ADAPTER.md del proyecto)
2. Ejecutar el flujo
3. Verificar el resultado
```

## Adaptadores conocidos

Lista de proyectos donde ya vive instalada (se rellena con el uso real):

- _(ninguno aún)_

## Referencias

| Recurso | Ruta |
|---------|------|
| Ciclo de vida | `.agents/rules/ciclo-vida-skills.md` |
| Changelog | `CHANGELOG.md` (junto a este archivo) |
| Patrón origen | `C:\Users\angel\Desktop\CalendarFinace\.agents\skill\agents-architecture` |
