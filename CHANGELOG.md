# Registro de cambios

## v2 — 16 de noviembre de 2026 · `financial-anomaly-detector-v2`

Auditoría completa de la v9.3 y prueba fuera de muestra.

### Corregido
- **Fuga de información.** Componentes del modelo y umbrales se ajustaban con toda la muestra. Ahora el modelo se reentrena periódicamente solo con datos anteriores y los umbrales se calibran sobre días que el modelo de calibración no vio. Prueba de truncación en SPY: 19 señales cambiaban en la v9.3; 0 en la v2.
- **Datos de SPAC.** SOFI, GRAB y JOBY empiezan en su fecha de listado, verificada en SEC EDGAR.
- **Error de signo** en el puntaje de uno de los tipos de señal.

### Agregado
- Protocolo prerregistrado con periodo de desarrollo (2020 a 8-abr-2026) y periodo de prueba (desde el 9-abr-2026), corrido una sola vez.
- Línea base: regla simple de volatilidad con la misma frecuencia de alertas que el SOM.
- Evaluación contra el modelo HAR en panel (10 activos, efecto fijo, errores Driscoll-Kraay) con corrección de Benjamini-Hochberg sobre 7 pruebas.
- Conteo por episodios, robustez con el VIX (SPY) y diagnóstico por grupos.
- Cuatro figuras con marca de agua y licencia.
- `LICENSE` en dos capas: contenido del repositorio bajo CC BY-NC-ND 4.0; código privado, todos los derechos reservados.

### Retirado
- La métrica de acierto contra 50% (incluida la señal "Neutral"), la elección de la "mejor ventana" por resultado y la validación con eventos macro sin línea base.

### Resultado
- Prueba final: las 7 pruebas **no concluyentes** (p ajustado 0.93).

## v1 (v9.3) — 8 de abril de 2026 · `financial-anomaly-detector` (archivado)

Versión final del desarrollo iterativo (versiones 1 a 9.3). Sus errores conocidos están documentados en el `ISSUES.md` de ese repositorio.
