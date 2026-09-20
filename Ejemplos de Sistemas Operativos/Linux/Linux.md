**Tipo de Núcleo:** **[[Núcleo Monolítico]]** (con soporte para módulos dinámicos).
**Definición:** Es un núcleo (kernel) de sistema operativo libre y de código abierto de tipo UNIX, desarrollado originalmente por Linus Torvalds en 1991 bajo la licencia GNU GPL.

**Características e Info Clave:**

- **Estructura Monolítica:** Todas las funciones esenciales del sistema operativo (gestión de procesos, memoria, controladores de dispositivos, pilas de red y sistemas de archivos) se ejecutan juntas en el espacio de memoria privilegiado o **[[Modo Núcleo]]**.
- **Módulos Cargables:** A pesar de ser monolítico, permite cargar y descargar componentes (drivers, sistemas de archivos) dinámicamente en tiempo de ejecución sin necesidad de reiniciar el sistema.
- **Abstracción del Sistema de Archivos:** Implementa el **[[VFS]]** (Virtual File System) para gestionar múltiples formatos de archivos de forma unificada.
- **Entorno de Red:** La gestión de red, _sockets_ y tuberías está integrada de forma nativa en el propio núcleo.