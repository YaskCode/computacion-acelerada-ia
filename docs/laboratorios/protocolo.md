# Protocolo de benchmarking y evidencias TPU

1. Registra hipótesis, commit, modelo y revisión, datos sintéticos o versión de datos, semilla, framework, runtime, backend, hardware, número de dispositivos, forma, lote y precisión.
2. Fija la misma carga y semántica para comparar CPU/GPU/TPU. Reporta por separado los experimentos con lotes, versiones o precisión diferentes. Valida calidad con referencia y tolerancia o métrica pertinente.
3. Distingue preparación y transferencia, primera llamada con compilación cuando corresponda, estado estable y tiempo extremo a extremo. Calienta cada configuración, sincroniza antes de cerrar el cronómetro y conserva muestras crudas. Usa las mismas repeticiones en cada comparación.
4. Registra mediana, p95, throughput y memoria/utilización cuando estén disponibles. Indica tamaño de muestra, unidad, método de percentil y alcance. Speedup = latencia de referencia / latencia candidata. Reducción de latencia (%) = 100 × (referencia − candidata) / referencia.
5. Marca cada backend como medido, no disponible, incompatible o no probado, con motivo. Una ejecución CPU puede validar el procedimiento. El informe debe distinguir cobertura de la prueba, diseño propuesto y resultados medidos.

## Registro de evidencia

Una fila por configuración. Guarda archivo de muestras y enlace de commit en el repositorio del equipo.

| Backend y dispositivo | Configuración y alcance | Estado | Muestras | p50/p95 | Throughput | Calidad | Evidencia y limitaciones |
|---|---|---|---|---|---|---|---|
| CPU, GPU o TPU | Modelo, forma, precisión, lote y versiones | Por completar | — | — | — | — | — |

Para una posible reutilización en Google TPU Builder conserva un README reproducible, dependencias fijadas, generación de datos, comandos, modelo y topología TPU reales, perfiles exportables, muestras, controles numéricos y hallazgos con limitaciones. Antes de compartir, retira datos personales, credenciales e identificadores de infraestructura privada.
