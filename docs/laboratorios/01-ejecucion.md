# Laboratorio 1 · Ejecución y selección de infraestructura

**Objetivo.** Detectar el backend, medir una carga tensorial y decidir cómo trasladar el procedimiento a un componente Wellness.

1. En un entorno Python aislado instala JAX según la [guía oficial](https://docs.jax.dev/en/latest/installation.html). Para una línea base CPU usa `python -m pip install jax` y `JAX_PLATFORMS=cpu python bench.py` en una shell POSIX. Conserva las versiones con `python -m pip freeze`. En GPU o TPU utiliza la instalación compatible del entorno y verifica el dispositivo impreso antes de registrar la ejecución.
2. Guarda este ejemplo docente como `bench.py`. El tiempo de la primera llamada incluye compilación cuando corresponda. La medición posterior excluye la preparación y transferencia inicial del tensor.

```python
from statistics import median
from time import perf_counter

import jax
import numpy as np

def multiply(matrix):
    return matrix @ matrix.T

def measure(operation, matrix):
    start = perf_counter()
    result = operation(matrix).block_until_ready()
    return (perf_counter() - start) * 1000, result

host_matrix = np.random.default_rng(0).random((512, 512), dtype=np.float32)
matrix = jax.device_put(host_matrix, jax.devices()[0]).block_until_ready()
print(jax.__version__, jax.default_backend(), jax.devices(), matrix.shape, matrix.dtype)
reference = host_matrix @ host_matrix.T

for label, operation in (("sin jit explícito", multiply), ("jit", jax.jit(multiply))):
    first_ms, result = measure(operation, matrix)
    for _ in range(3):
        measure(operation, matrix)
    samples = [measure(operation, matrix)[0] for _ in range(30)]
    np.testing.assert_allclose(np.asarray(result), reference, rtol=1e-4, atol=1e-4)
    print(label, "primera llamada ms:", first_ms, "mediana ms:", median(samples))
    print("muestras ms:", samples)
```

3. Repite en los dispositivos disponibles con el [protocolo](protocolo.md). En el equipo, sustituye el ejemplo por una carga delimitada de Wellness, como embeddings locales o una operación de inferencia, y define su prueba de equivalencia.

**Resultado esperado.** Backend identificado, verificación numérica y muestras por ejecución. **Evidencia.** Comando, entorno, salida cruda, tabla, diagrama de ejecución y limitaciones. El ejemplo sintético valida el instrumento. La evidencia del componente corresponde al [Sprint 1](../sprints/01-ejecutar.md).
