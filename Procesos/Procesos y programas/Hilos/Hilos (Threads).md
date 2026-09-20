Un **hilo** (o proceso ligero) es un flujo de ejecución dentro de un **[[Proceso]]** que comparte la imagen de memoria (espacio de direcciones) y otros recursos con otros hilos del mismo proceso.
## Estructura y Uso de la CPU

Los sistemas operativos que ejecutan procesos con múltiples hilos usan con más eficiencia la CPU. El sistema intercala la ejecución de procesos entre el cómputo en la CPU y las operaciones de **[[Entrada y Salida (E-S)|Entrada/Salida (E/S)]]**.

### Modelo de Memoria (Monohilo vs. Multihilo)
* **Proceso Monohilo:** Contiene un único espacio de direcciones con un solo hilo ($T$) ejecutando.
* **Proceso Multihilo:** Varios hilos ($T$) coexisten compartiendo el mismo espacio de direcciones del proceso padre.

## Motivaciones para el Uso de Hilos

1. **Menor sobrecarga:** La sobrecarga involucrada en la creación de un proceso es mayor que en la de un hilo.
2. **Conmutación rápida:** La permutación de contexto entre hilos del mismo proceso es más rápida que entre procesos independientes.
3. **Paralelismo con llamadas bloqueantes:** Permite combinar el paralelismo con la ejecución secuencial y las **[[Llamada al Sistema]]** bloqueantes.
4. **Compartición eficiente de recursos:** Todos los hilos de un proceso comparten el mismo espacio de direcciones en la **[[Memoria Principal]]**, facilitando el intercambio de datos.


## 📂 Sub-secciones de Hilos

* **[[Implementación de Hilos]]**: Diferencias entre hilos gestionados en espacio de usuario (ULT) vs. espacio de núcleo (KLT).
* **[[Modelos y Diseño de Hilos]]**: Patrones de organización (despachador, pipeline, equipo) y primitivas de diseño.