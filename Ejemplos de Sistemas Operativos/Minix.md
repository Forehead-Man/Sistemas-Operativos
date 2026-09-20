**Tipo de Núcleo:** **[[Micronúcleo]]** (Microkernel).

**Definición:** Es un sistema operativo tipo UNIX con arquitectura de micronúcleo, creado por el profesor Andrew S. Tanenbaum en 1987 con fines netamente educativos e ilustrativos para enseñar el funcionamiento interno de un SO.

**Características e Info Clave:**

- **Filosofía de Micronúcleo:** Mantiene en el espacio de **[[Modo Núcleo]]** únicamente las funciones mínimas indispensables (comunicación interproceso, planificación básica de CPU y manejo básico de interrupciones).

- **Servicios en [[Modo Usuario]]:** A diferencia de un núcleo monolítico, los controladores de dispositivos (drivers), los sistemas de archivos y la gestión de red se ejecutan como procesos independientes fuera del núcleo en modo usuario.

- **Tolerancia a Fallos y Aislamiento:** Si un controlador de dispositivo (por ejemplo, el driver de red) falla o colapsa, simplemente se reinicia el proceso en espacio de usuario sin tumbar todo el sistema ni comprometer la memoria del núcleo.
