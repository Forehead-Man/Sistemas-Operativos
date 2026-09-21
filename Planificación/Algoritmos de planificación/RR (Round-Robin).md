Muy usado en sistemas de tiempo compartido.

- Se asigna a cada proceso de la cola de listos un intervalo de tiempo de CPU llamado **time-slice** o **quantum**.
- Los procesos van tomando la CPU por turnos y por el tiempo que indique el quantum
- Al cumplirse el tiempo, el proceso es desalojado mediante una interrupción y retornado a la cola de listos.

También puede suceder que el proceso haya terminado o que entre en una
operación de entrada/salida. En ese caso el planificador selecciona otro de la
cola de listos.

- Equitativo y ordenado
- Tiempo de espera promedio largo