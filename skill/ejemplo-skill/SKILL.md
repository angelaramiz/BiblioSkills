# SKILL de ejemplo: mi-primera-skill

> Plantilla de ejemplo — duplícala como `skill/<nombre-skill>/SKILL.md` y borra este directorio cuando tengas tu primera skill real.

## Resumen

Describe en 2-3 líneas qué capacidad aporta esta skill y cuándo debe usarla el agente.

## Estructura

```
skill/mi-primera-skill/
├── SKILL.md            # Documentación de la skill (este archivo)
├── scripts/            # Scripts auxiliares (opcional)
└── assets/             # Plantillas o recursos (opcional)
```

## Componentes clave

1. **Disparador**: cuándo se activa (p. ej. "el usuario pide X").
2. **Entradas**: qué contexto necesita (archivos, rutas, parámetros).
3. **Salidas**: qué produce (archivos, cambios, decisiones).

## Flujo de trabajo del agente

```
1. Leer la tarea en `.agents/input.md`
2. Reunir las entradas (sin inventar rutas ni endpoints)
3. Ejecutar los pasos de la skill
4. Actualizar `.agents/tasks.md` y registrar decisiones
```

## Instalación / uso

```bash
# Ejemplo: copiar la skill a otro proyecto
cp -r skill/mi-primera-skill /ruta/otro-proyecto/.agents/skill/
```

## Referencias

| Recurso | Ruta |
|---------|------|
| Patrón de referencia | `C:\Users\angel\Desktop\CalendarFinace\.agents\skill\agents-architecture` |
| Reglas del repo | `AGENTS.md` |
