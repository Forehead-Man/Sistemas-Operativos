### `strace`

**Definición:** Herramienta de diagnóstico que intercepta, registra y muestra por pantalla (`stderr`) todas las **[[Llamada al Sistema|Llamadas al Sistema]]** y señales que efectúa un proceso durante su ejecución.
- **Ejemplo práctico:** Al ejecutar `strace cat /dev/null`, permite ver la secuencia exacta desde la carga del programa (`execve`), la apertura del archivo (`openat`), la lectura (`read`) y la finalización (`exit_group`).

### `dmesg`

**Definición:** Comando que imprime el búfer circular (_ring buffer_) de mensajes del núcleo.

**Uso:** Esencial para auditar la secuencia de arranque del sistema, la detección de dispositivos plug-and-play (USB, discos) y los errores internos del kernel.