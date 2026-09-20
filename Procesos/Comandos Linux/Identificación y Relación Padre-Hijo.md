**`PID` (Process Identifier):** Número entero único asignado por el sistema operativo a cada proceso activo en el sistema.

**`PPID` (Parent Process Identifier):** Identificador único del proceso padre que creó al proceso actual.

**[[Llamada al Sistema|Llamadas al sistema]] para consultar:**
- `getpid()`: Retorna el PID del proceso en ejecución.
- `getppid()`: Retorna el PPID del proceso padre (usualmente el shell que lanzó la aplicación).

Todo proceso es creado por otro proceso (padre), formando una estructura en jerarquía de árbol.