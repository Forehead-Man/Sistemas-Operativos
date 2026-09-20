**Definición:** API estándar para la creación y sincronización de [[Hilos (Threads)|hilos]] a nivel de software en C para sistemas tipo UNIX/Linux.
- **Funciones Clave:**
    - `pthread_create()`: Crea un nuevo hilo que ejecutará una función de manera concurrente compartiendo la memoria del proceso.
    - `pthread_join()`: Bloquea al hilo invocador (usualmente el hilo principal) hasta que el hilo especificado finalice su ejecución (mecanismo de sincronización).

**Compilación:** Requiere enlazar la biblioteca explícitamente agregando la opción `-pthread` a `gcc` (ej. `gcc -pthread -o programa programa.c`).

- **Seguimiento con `strace`:** La opción `strace -f` permite rastrear las llamadas al sistema incluyendo los nuevos hilos y procesos hijos creados dinámicamente. ([[Herramientas de Trazado y Diagnóstico del Kernel]])