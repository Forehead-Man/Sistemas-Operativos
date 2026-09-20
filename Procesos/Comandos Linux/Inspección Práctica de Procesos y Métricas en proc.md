### Comando ps y top

- **`ps` (Process Snapshot):** Captura el estado estático de los [[Proceso|procesos]] en un instante determinado.
    - `ps aux` / `ps -fu "$USER"`: Lista los procesos de todos los usuarios o de un usuario particular con detalles de recursos.
    - `pstree -p`: Muestra la jerarquía de procesos en forma de árbol con sus PID.
    - `ps -T -p <PID>`: Lista todos los **hilos** pertenecientes a un proceso específico.

- **`top` / `htop`:** Monitor dinámico en tiempo real que ordena los procesos según su consumo de recursos.
    - `top -H`: Alterna la vista para mostrar los hilos en lugar de solo los procesos.

### /proc/self y status

- **`/proc/self`:** Enlace simbólico especial dentro de [[procfs (Proc Filesystem)|procfs]] que apunta automáticamente al directorio `/proc/<PID>` del proceso que realiza la consulta en ese preciso instante.
- **`/proc/<PID>/status`:** Archivo que expone información del proceso, incluyendo su estado, [[Identificación y Relación Padre-Hijo|PID, PPID]] y métricas precisas de cambios de contexto:
    - `voluntary_ctxt_switches`: Conteo de cambios de contexto voluntarios (por bloqueos de E/S o esperas).
    - `nonvoluntary_ctxt_switches`: Conteo de cambios de contexto involuntarios (expiración de _quantum_ por el planificador).