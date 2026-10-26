---
name: arquitectura-android
version: 0.1.0
description: Repositorios de referencia para arquitectura Android (Clean Architecture, MVVM/MVI, modularización, offline-first). Usar al estructurar una app Kotlin o decidir patrones de capas.
---

# SKILL: arquitectura-android

## Resumen

Índice curado de 6 repositorios externos de referencia para estructura y
arquitectura de apps Android en Kotlin. Son solo lectura: aquí vive el
procedimiento de consulta, nunca su contenido.

## Referencias verificadas (oct-2026)

| Repo | Enfoque verificado | Licencia | Consultar cuando |
|------|--------------------|----------|------------------|
| https://github.com/android/nowinandroid | Referencia oficial Google: Compose, guía oficial de arquitectura + modularización, Hilt, dobles de prueba sin mocks, Roborazzi, sabores demo/prod, baseline profiles | Apache-2.0 | Base oficial y modularización |
| https://github.com/android/architecture-samples | Misma app TODO en varias ramas; MVVM/MVI, Compose, Room + remoto fake, sabores mock/prod, Hilt | Apache-2.0 | Comparar patrones de capas sobre el mismo problema |
| https://github.com/skydoves/MarvelHeroes | MVVM + repositorio + **Koin** (no Hilt), Coroutines, Room, Retrofit/OkHttp; stack 2020 (minSdk 21) | Apache-2.0 | Ejemplo de patrón repositorio; ojo: datado, no copiar DI ni UI |
| https://github.com/igorwojda/android-showcase | Template: módulos por feature con presentación/dominio/datos, MVVM+MVI, Koin, convention plugins, catálogo de versiones, Konsist/Ktlint/Detekt | MIT | Estructura de módulos y calidad (convenciones + CI) |
| https://github.com/bufferapp/clean-architecture-components-boilerplate | Boilerplate por capas (mobile-ui/presentation/domain/data/remote/cache), ViewModels + UseCases, caché Room; stack RxJava2/Dagger de su época | MIT | Anatomía exhaustiva de capas; datado en libs, vigente en estructura |
| https://github.com/jshvarts/OfflineSampleApp | Offline-first: escribir primero en Room + sync diferida en job persistente; dos ramas (observador en foreground vs background) | Apache-2.0 | Capa de datos offline y colas de sincronización |

## Uso

1. Definir `{{decision}}` en una línea (qué capa o patrón está en juego).
2. Consultar en este orden: nowinandroid (base) → architecture-samples
   (comparar) → showcase (módulos/calidad) → el específico
   (MarvelHeroes / buffer / OfflineSampleApp según el tema).
3. Verificar vigencia antes de copiar: los boilerplates 2017–2020 usan
   libs viejas (RxJava2, Dagger 2.11, DataBinding); aprovechar la estructura,
   no las dependencias.
4. Registrar la decisión y el porqué en el `ADAPTER.md` o decisiones del proyecto.

## Reglas

- Enlazar, nunca copiar: respetar licencias (Apache-2.0/MIT exigen atribución).
- Si el proyecto ya usa un DI (Koin/Hilt) o async (Coroutines/Flow), la
  referencia no lo cambia: solo informa la estructura.
- Correcciones a descripciones habituales: MarvelHeroes es MVVM+Koin (no
  MVI+Hilt); la URL correcta de Buffer lleva sufijo `-boilerplate`; la de
  offline-first es `jshvarts/OfflineSampleApp` (no `jshvartsman/offlinefirst`).

## Variables del proyecto

| Variable | Descripción | Ejemplo |
|----------|-------------|---------|
| `{{decision}}` | Decisión de arquitectura a tomar | `cómo separar repo local/remoto en la capa de datos` |
| `{{patron}}` | Patrón en evaluación | `MVVM`, `MVI`, `Clean por feature` |

## Adaptadores conocidos

- _(ninguno aún — v0.1.0 en evaluación, pendiente de primer uso real)_

## Referencias

| Recurso | Ruta |
|---------|------|
| Changelog | `CHANGELOG.md` (junto a este archivo) |
| Skills hermanas | `skill/movil/android-kotlin-app`, `skill/movil/emulador-android`, `skill/movil/ota-android-generic` |
