- **Basado en hilos:** Windows **planifica hilos, no procesos**. El proceso solo actúa como un contenedor de recursos y contexto para sus hilos.
- **Mecanismo general:** Es un sistema **con desalojo basado en prioridades**. Siempre se elige el hilo listo con mayor prioridad.
- **Asignación de tiempo (_Quantum_):**
    - Los hilos ejecutan durante una ráfaga de tiempo (_quantum_).
    - Su duración varía según la configuración del sistema (largos/cortos), si el proceso está en primer o segundo plano, o por uso de objetos de trabajo.
    - Un hilo de mayor prioridad puede desalojar al actual antes de que agote su _quantum_.
- **Estructura del código:** No existe un módulo único o centralizado; el código está distribuido en el núcleo y se lo conoce como **activador del núcleo** (_kernel dispatcher_).
- **Eventos que activan la planificación:** Se evalúa qué hilo ejecutar (y se hace cambio de contexto) cuando:
    - Un hilo pasa a estar listo (recién creado o desbloqueado).
    - Un hilo termina su _quantum_, finaliza o entra en espera.
    - Cambia la prioridad de un hilo (por llamada al sistema o por el propio SO).
    - Cambia la afinidad de procesador en sistemas multiprocesador.

### Niveles de prioridad

32 niveles de prioridad (16 para tiempo real (16 al 32), 15 niveles variables (1 al 15) y el nivel 0 de sistema, reservado para el hilo de página cero.
- Tanto la API de Windows como el Núcleo pueden asignar prioridades a hilos.
- La prioridad base de un hilo se hereda del proceso que la creó y luego puede ser modificada.![[Niveles prioridad windows.png|582]]Ver [[Base de datos del activador (Dispatcher Database) en Windows]]