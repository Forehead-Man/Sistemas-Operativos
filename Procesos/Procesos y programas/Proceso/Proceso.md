**Definición:** Un proceso es una instancia de un [[programa]] (un [[programa]] en ejecución).

**Un proceso es:**
- Es dinámico.
- Tiene [[contador de programa]].
- Su ciclo de vida comprende desde que [[Creación y terminación de procesos|se lo “dispara”]] hasta que termina.

## Estados de un proceso

**Estados de un proceso:** Un proceso es dinámico, cambia su estado a medida que se ejecuta.
### Modelo simplificado (3 estados)
 Como mínimo un proceso puede estar en uno de los siguientes 3 estados:
- **Ejecutándose (running):** un proceso que está ejecutando en una CPU. Si un sistema tiene *n* CPUs puede tener como máximo *n* procesos en ese estado.
- **Bloqueado (blocked):** el proceso está esperando que ocurra algún evento, como por ejemplo la finalización de una operación de entrada o salida.
- **Listo (ready):** un proceso que no está asignado a la CPU pero está listo para ejecutar. Un proceso listo podría ejecutar si se lo asigna a una CPU.
![[Pasted image 20260916011522.png]]

### Modelo ampliado (5 estados)

- **Nuevo (new):** también llamado “creado”, espera admisión al estado “listo”.
- **Listo (ready):** también llamado “esperando”, ha sido cargado en memoria principal y espera que el despachador lo ponga a ejecutar. Puede haber varios procesos en este estado.
- **Bloqueado (blocked):** un proceso que está esperando que ocurra un evento antes de que pueda continuar. Con frecuencia, este evento es la finalización de una operación de entrada o salida.
- **Terminado (terminated):** un proceso que ha detenido su ejecución pero el sistema operativo aún mantiene un registro de él (en UNIX, a estos procesos se les suele llamar “zombie”).

### Estados en sistemas con Memoria Virtual (7 estados)

En sistemas con memoria virtual o mecanismo de _swapping_ (intercambio), los procesos pueden ser llevados a memoria secundaria para liberar espacio en la **[[Memoria Principal]]**
- **Intercambiado y esperando:** también se lo denomina “suspendido y esperando”, fue sacado de la memoria principal y almacenado en [[Memoria virtual|memoria secundaria]].
- **Intercambiado y bloqueado:** o “suspendido y bloqueado”; un proceso que estaba bloqueado también puede pasar a residir en el área de swap.
![[Pasted image 20260916012401.png]]

### Gestión de Transiciones de Estado

Las transiciones de estado no son gestionadas únicamente por un solo componente, sino por distintos módulos del **[[Núcleo (Kernel)]]**:

- **Planificación de CPU:** El **[[Planificador (Scheduler) y activador (Dispatcher)|planificador (scheduler)]]** es el encargado específico de administrar las transiciones entre los estados **Listo**, **Ejecutándose** y la reincorporación a la cola de listos (por ejemplo, cuando expira el quantum de tiempo en sistemas multiprogramados).
- **Entrada/Salida y Eventos:** Las transiciones hacia y desde el estado **Bloqueado** son manejadas por los gestores de **[[Entrada y Salida (E-S)|Entrada/Salida (E/S)]]** e **[[Interrupciones]]**.
- **Ciclo de Vida:** La creación (**Nuevo**) y destrucción (**Terminado**) de procesos son gestionadas por el subsistema de administración de procesos y memoria del **[[Sistema Operativo]]**.

