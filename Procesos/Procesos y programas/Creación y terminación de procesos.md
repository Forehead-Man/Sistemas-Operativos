En Unix, un [[Proceso]] crea a otro a través de una llamada a sistema
**fork()** El creador es el proceso padre y el creado el hijo. Estructura de árbol.

- El padre puede puede continuar ejecutándose concurrentemente con sus hijos o esperar que sus hijos hayan terminado.
- Un proceso termina cuando ejecuta su última instrucción y [[Llamada al Sistema|solicita al sistema operativo]] que lo elimine
- Con **fork()** los procesos se clonan. Ambos procesos continúan su ejecución con la instrucción siguiente al **fork()**. El código de retorno que recibe el hijo es 0, el del padre es el PID (Process ID) del hijo.
- Si el hijo invoca **execve()** se reemplaza con un programa nuevo.
- El padre puede esperar la finalización del hijo con **wait()**.