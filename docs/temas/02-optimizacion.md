# Optimización del Entrenamiento e Inferencia de Modelos de Inteligencia Artificial

Perfila antes de intervenir. Separa lectura y preparación, transferencias, compilación, cómputo y esperas. Compara entrenamiento por tiempo por paso o por ejemplos procesados, manteniendo un criterio de calidad. En inferencia, mide latencia por solicitud y throughput bajo un lote y concurrencia definidos.

| Señal del perfil | Intervención para contrastar | Control |
|---|---|---|
| Muchas operaciones pequeñas | JIT y fusión mediante XLA | Compilación inicial y exactitud |
| Presión de memoria | Precisión mixta y ajuste de lote | Desviación numérica y estabilidad |
| Capacidad ociosa | Vectorización o agrupación de solicitudes | Latencia de cola y memoria |
| Capacidad de un dispositivo insuficiente | Paralelismo de datos o de modelo | Comunicación, sincronización y calidad |

En paralelismo de datos se replica el modelo y se divide el lote. En paralelismo de modelo se reparten sus operaciones o estados. En ambos casos registra topología, lote global y comunicación antes de atribuir una mejora al número de dispositivos. La precisión mixta combina tipos según la sensibilidad de cada operación. Compara resultados con tolerancias justificadas y examina errores, pérdida o calidad antes de aceptar una configuración.

[Laboratorio](../laboratorios/02-optimizar.md) · [Sprint 2](../sprints/02-optimizar.md)
