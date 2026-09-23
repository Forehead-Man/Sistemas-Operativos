[[Comunicación e IPC (Inter-Process Communication)]]

Cuando queremos comunicar o sincronizar dos procesos y no contamos con una memoria compartida como los casos que hemos visto hasta ahora, se debe recurrir al pase de mensajes.
- Los procesos pueden ser remotos (máquinas distintas) o locales.
- Normalmente en este tipo de comunicaciones, un proceso suele ser más lento que el otro, en estos casos se debe recurrir al uso de [[Memoria intermedia o Buffer|memorias intermedias o Buffers]].
### Primitivas Básicas: `send()` y `receive()`

Para que dos procesos se comuniquen, utilizan dos operaciones fundamentales:

- **`send()`**: Enviar un mensaje a otro proceso.
- **`receive()`**: Recibir un mensaje de otro proceso.

Ambas primitivas pueden configurarse de dos formas (semántica de comunicación):

- **Bloqueante (Síncrona):** El proceso que ejecuta la instrucción se detiene (se suspende) hasta que la operación se completa o se confirma.
- **No bloqueante (Asíncrona):** El proceso envía o consulta por un mensaje e inmediatamente continúa con su ejecución sin esperar.
### Formas de enterarse de un mensaje en `receive()` no bloqueante

Cuando el receptor no se queda esperando bloqueado, necesita una forma de saber si llegó un nuevo mensaje:
- **Consulta (_polling_):** El receptor le pregunta periódicamente al sistema operativo si llegó un mensaje.
- **Interrupción:** El sistema operativo le avisa al proceso mediante un evento o señal en el instante en que llega el mensaje.
### Modo Síncrono

Se considera que la comunicación es estrictamente **Síncrona** cuando **tanto `send()` como `receive()` son bloqueantes**:
1. **Receptor:** Ejecuta `receive(mns)` y **suspende su ejecución** a la espera de que alguien le envíe un dato.
2. **Transmisor:** Ejecuta `send(mns)` para enviar el mensaje y **también suspende su ejecución**. No puede continuar hasta estar seguro de que el receptor recibió la información.
3. **Recepción:** Llega el mensaje al Receptor, este **reanuda su ejecución** y le envía una confirmación (_ack_ - _acknowledgment_).
4. **Confirmación:** Cuando el Transmisor recibe el _ack_, finalmente **reanuda su ejecución**.
![[Sincronizacion en pase de mensajes.png]]