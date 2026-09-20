La activación del sistema operativo se realiza mediante el mecanismo de las [[Interrupciones|interrupciones]]. Cuando se produce una interrupción se realizan las dos operaciones siguientes:

- Se salva el estado del procesador en el correspondiente [[PCB (Process Control Block)|PCB]].
- Se pasa a ejecutar la rutina de tratamiento de interrupción del sistema operativo.

A esto se le denomina cambio de contexto.

*El tiempo de conmutación de contexto es exclusivamente gasto extra (overhead), porque el sistema no realiza trabajo útil durante la conmutación.*

**Al tiempo entre detener un proceso y comenzar a correr otro se le llama “latencia de activación” o dispatch latency**