# Fundamentos de la Computación Acelerada para Inteligencia Artificial

La ingeniería de infraestructura para IA selecciona hardware, entorno de ejecución y compilador según la carga. Una CPU resulta útil para lógica de control, preparación de datos y líneas base. Una GPU puede aprovechar paralelismo masivo con lotes y operaciones compatibles. Una TPU está orientada a operaciones tensoriales con un ecosistema de ejecución específico. En un sistema heterogéneo, el host prepara datos y coordina dispositivos, de modo que memoria, transferencias y sincronización forman parte del análisis.

| Alternativa | Pregunta para seleccionarla |
|---|---|
| CPU | ¿La carga es pequeña, irregular o depende principalmente de red y E/S? |
| GPU | ¿Hay trabajo paralelo suficiente, kernels compatibles y memoria para el lote? |
| TPU | ¿La carga tensorial, el framework, las formas y los tipos de datos son compatibles con el entorno disponible? |

JAX ofrece transformaciones como JIT, diferenciación automática y vectorización. TensorFlow permite compilar funciones compatibles con XLA. PyTorch/XLA conecta el modelo PyTorch con dispositivos XLA. XLA puede fusionar operaciones y especializar la compilación según formas y tipos. AI Hypercomputer introduce la coordinación de infraestructura, software y servicios para cargas de IA.

Para seleccionar entorno, registra dispositivo, memoria, versiones, cuota y costo estimado. En Wellness, separa el cómputo local de llamadas a modelos remotos. Acelerar un componente local solo puede reducir la fracción de tiempo atribuible a ese componente.

[Laboratorio](../laboratorios/01-ejecucion.md) · [Sprint 1](../sprints/01-ejecutar.md)
