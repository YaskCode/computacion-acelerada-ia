# Herramientas, infraestructura y costos

| Escenario | Entorno | Comprobación previa |
|---|---|---|
| Desarrollo y línea base | Python local, Codespaces o Colab | Versiones, memoria, acceso al repositorio y backend CPU |
| Comparación acelerada | GPU o TPU compatible, con JAX, TensorFlow o PyTorch/XLA | Dispositivo real, soporte de operaciones, memoria, runtime, región y cuota cuando aplique |
| Serving e integración | Contenedor local o servicio cloud, por ejemplo Cloud Run, Kubernetes o Vertex AI según arquitectura | Contrato, acceso, región, cuotas, observabilidad y configuración de escalado aplicable |

GitHub conserva decisiones, entregas y evidencias. Mermaid facilita diagramas, Docker facilita empaquetado y Hugging Face puede proveer modelos o datasets con licencias compatibles. El equipo fija dependencias, versiones del modelo y origen de datos.

Antes de usar recursos facturables, confirma permisos, SKU, región, unidad de cobro y límites del proyecto. Estima cada partida como cantidad × tarifa de la unidad correspondiente. Suma cómputo, almacenamiento, tráfico y observabilidad aplicables. Para costo por mil solicitudes exitosas, divide el costo del escenario entre las solicitudes exitosas del mismo periodo y multiplica por mil. Registra moneda, fecha, fuente, supuestos y distinción entre estimación y factura. Define tiempo máximo de uso y verifica la eliminación de recursos temporales.

- [Precios de Cloud TPU](https://cloud.google.com/tpu/pricing)
- [Precios de Vertex AI](https://cloud.google.com/vertex-ai/pricing)
- [Calculadora de Google Cloud](https://cloud.google.com/products/calculator)
