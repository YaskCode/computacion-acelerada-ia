# Laboratorio 2 · Profiling y optimización

**Objetivo.** Explicar el efecto de una optimización con un experimento controlado.

1. Usa el comando y commit del Sprint 1 como línea base. Fija entradas, calidad, tamaño de lote, dispositivo y alcance. Usa un conjunto representativo de solicitudes para inferencia o una secuencia fija de pasos para entrenamiento.
2. Captura un perfil en estado estable con el profiler del framework. En JAX, ejecuta las iteraciones dentro de `with jax.profiler.trace("traces/baseline"):` y sincroniza la última salida dentro del bloque. Si la traza no está disponible, instrumenta preparación, inferencia y serialización con temporizadores y registra la limitación.
3. Selecciona un cuello de botella. Introduce un solo cambio medible, por ejemplo JIT, vectorización o precisión mixta. Si aplicas paralelismo, registra la estrategia, el lote global y los dispositivos.
4. Repite con el [protocolo](protocolo.md), conserva trazas por configuración y valida la calidad. Explica el efecto por métrica, incluyendo regresiones y variabilidad.

**Resultado esperado.** Comparación reproducible y decisión sustentada sobre mantener, ajustar o revertir el cambio. **Evidencia.** Commit, trazas o medición por etapas, datos crudos, métricas antes/después y prueba de calidad. Alimenta el [Sprint 2](../sprints/02-optimizar.md).
