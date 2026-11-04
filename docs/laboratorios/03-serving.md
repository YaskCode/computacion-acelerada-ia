# Laboratorio 3 · Serving y pruebas de carga

**Objetivo.** Verificar un contrato de inferencia e identificar el comportamiento del servicio bajo carga.

1. Empaqueta el componente optimizado, fija versiones y expón `GET /health` y `POST /predict` o sus equivalentes. Documenta URL, ejemplo JSON sintético, respuesta esperada, manejo de errores, timeout y comando de arranque. Prueba el endpoint desde Wellness y desde un cliente HTTP.
2. Verifica con `curl -fsS --max-time 10 "$BASE_URL/health"` y `curl -fsS --max-time 10 -H 'Content-Type: application/json' --data @request.json "$BASE_URL/predict"`. Para una entrada inválida registra código HTTP y cuerpo. Usa autenticación cuando el entorno la requiera.
3. Con un generador de carga como k6, repite la misma mezcla de solicitudes durante 60 segundos con 1, 4 y 8 clientes virtuales, ajustando si el entorno lo requiere. Usa un timeout fijo, mide desde el cliente, guarda el resumen de cada prueba y registra condiciones iniciales y de calentamiento.
4. Registra p50/p95, solicitudes exitosas por segundo, errores, CPU/memoria y réplicas disponibles. Correlaciona la carga con logs y métricas. Si solo hay entorno local, mide allí y deja el autoescalado cloud como diseño con prueba pendiente.
5. Calcula el costo de un escenario según la [guía de infraestructura](../recursos/infraestructura.md). Tras una prueba cloud autorizada, elimina los recursos temporales y revisa consumo.

**Resultado esperado.** Endpoint funcional en el entorno declarado, integración comprobada y límites de operación documentados. **Evidencia.** Solicitudes y respuestas anonimizadas, configuración, reporte de carga, telemetría y estimación trazable. Alimenta el [Sprint 3](../sprints/03-escalar.md).
