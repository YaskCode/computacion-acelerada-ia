# Escalabilidad e Infraestructura para Aplicaciones Modernas de Inteligencia Artificial

El servicio de inferencia establece un contrato de entrada, salida, error y versión. En Wellness, el orquestador consume ese contrato y el servicio carga una versión identificable del modelo. Un contenedor portable, un endpoint administrado o una plataforma de orquestación ofrecen distintos niveles de control sobre hardware y operación. AI Hypercomputer sirve de referencia para evaluar el conjunto de aceleradores, redes, software y servicios administrados.

Define un objetivo de servicio para latencia y errores, y mide con demanda estable, ráfagas y recuperación. Observa solicitudes, p50/p95, errores, concurrencia, colas, réplicas y utilización cuando exista telemetría. Compara arranque en frío y servicio caliente. Describe señal de autoescalado, mínimo y máximo de réplicas, tiempo de reacción y capacidad ante saturación.

Para decidir entre configuraciones usa costo por solicitud exitosa junto con latencia y tasa de éxito. Registra las dependencias remotas y sus límites. Valida salud, timeouts, control de acceso y reversión antes de proponer la puesta en producción.

[Laboratorio](../laboratorios/03-serving.md) · [Sprint 3](../sprints/03-escalar.md)
