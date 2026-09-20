---
padre: "[[Hilos (Threads)]]"
---
Un paquete de hilos puede ser implementado ya sea en el espacio de usuario o en el espacio de núcleo.

## 1. Implementación en Espacio de Usuario (ULT - User-Level Threads)

Los hilos corren sobre un **sistema runtime** (biblioteca en **[[Modo Usuario]]**) que se encarga de manejarlos.

* **Estado:** Las llamadas del paquete de hilos se implementan como llamadas a procedimientos del sistema runtime.
* **Planificación:** Ocurre una planificación en dos niveles. El **[[Planificador (Scheduler) y activador (Dispatcher)|Planificador]]** del núcleo asigna *quantums* a los procesos pesados, y el planificador del runtime divide ese *quantum* entre sus hilos.
* **Transparencia:** **La existencia de hilos es invisible para el núcleo.**

## 2. Implementación en el Núcleo (KLT - Kernel-Level Threads)

No se utiliza un sistema runtime; los hilos son gestionados directamente por el **[[Núcleo (Kernel)]]**.

* **Estado:** La tabla con la información de estado de los hilos se mantiene dentro del núcleo.
* **Bloqueos:** Todas las llamadas que deberían bloquear a un hilo se implementan como **[[Llamada al Sistema|Llamadas al Sistema]]**.
* **Gestión:** Cuando un hilo se bloquea, el núcleo selecciona otro hilo para ser ejecutado.
* **Transparencia:** **La existencia de hilos es conocida por el núcleo.**

## Ventajas y Desventajas de Ambos Enfoques

### Enfoque en Espacio de Usuario (Runtime / ULT)
* **Ventajas:**
  * Se pueden implementar sobre cualquier sistema operativo.
  * Permite a los usuarios usar sus propios algoritmos de planificación para los hilos de un proceso.
	  * La permutación de contexto es extremadamente rápida (realizada por el runtime sin entrar a **[[Modo Núcleo]]**).
* **Desventajas:**
  * Dificultad en **[[Entrada y Salida (E-S)|Llamadas al Sistema Bloqueantes]]**: Si un hilo realiza una llamada bloqueante, **se detienen todos los demás hilos del proceso**.
  * No es posible aplicar políticas de *Round Robin* (turno circular) puras debido a la falta de interrupciones de reloj en espacio de usuario.

### Enfoque en Espacio de Núcleo (KLT)
* **Ventajas:** Si un hilo se bloquea en una operación de E/S, el núcleo puede planificar otro hilo del mismo proceso.
* **Desventajas:** Mayor sobrecarga al conmutar entre hilos, ya que requiere cambiar de modo mediante una llamada al sistema.