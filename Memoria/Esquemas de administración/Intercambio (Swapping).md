Mecanismos de administración de memoria que permiten liberar la RAM física disponible y ejecutar programas cuyo tamaño total supera la capacidad de la memoria principal, moviendo temporalmente bloques de información entre la [[Memoria Principal|RAM]] y la [[Memoria virtual|memoria secundaria]] (disco).

**Mecanismo:**
- **_Swap-out_ / _Page-out_:** Mueve datos desocupados de la RAM hacia el disco.
- **_Swap-in_ / _Page-in_:** Trae los datos de regreso del disco a la RAM cuando el proceso los necesita para ejecutarse.

**Implementación:**
- **Linux:** Utiliza una partición dedicada (_swap partition_) o un archivo de intercambio (_swapfile_).
- **Windows:** Utiliza un archivo de intercambio (como `pagefile.sys`).

**Encargado:** El **[[Planificador (Scheduler) y activador (Dispatcher)|planificador de mediano plazo]]** (_medium-term scheduler_) gestiona estas tareas de entrada y salida entre RAM y disco.

