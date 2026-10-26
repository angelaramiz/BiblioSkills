# Changelog — arquitectura-android

## [Unreleased]

## [0.2.0] — 2026-10-26

- Recorte a 2 referencias primarias (decisión del dueño): nowinandroid
  (dirección oficial) + android-showcase (estructura copiable).
- Descartadas a propósito, no re-agregar sin razón nueva:
  `architecture-samples` (enseña lo mismo que la guía oficial, en juguete),
  `MarvelHeroes` (MVVM+Koin datado, solo ejemplo mínimo de repositorio),
  `clean-architecture-components-boilerplate` (capas vigentes, libs 2017–2018),
  `OfflineSampleApp` (offline puntual; el patrón ya vive mejor en las colas
  propias PendingTx/PendingOp).

## [0.1.0] — 2026-10-26

- Alta como índice de referencias externas (no vendoreadas): 6 repos
  verificados (nowinandroid, architecture-samples, MarvelHeroes,
  android-showcase, clean-architecture-components-boilerplate,
  OfflineSampleApp) con enfoque, licencia y cuándo consultarlos.
- Correcciones incluidas: 2 URLs del mensaje origen daban 404
  (`bufferapp/clean-architecture-components` → `...-boilerplate`;
  `jshvartsman/offlinefirst` → `jshvarts/OfflineSampleApp`) y MarvelHeroes
  es MVVM+Koin, no MVI+Hilt.
- Estado: en evaluación, pendiente de primer uso real en un proyecto.
