# POSIX
- **Estándar IEEE (1996):** Define políticas de planificación para procesos e hilos.
- **Asignación:** Cada proceso/hilo tiene una política y un nivel de prioridad asociado.
- **Prioridades:** Mínimo 32 niveles por política; el planificador siempre elige la más alta.
- **Políticas principales:**
    - **FIFO:** First-In, First-Out (pero con desalojo por mayor prioridad).
    - **RR:** Round Robin.
    - **OTHER:** Varía según la implementación del sistema.
- **Convivencia y dinamismo:** Diferentes políticas pueden convivir a la vez y un proceso puede cambiar su prioridad o política dinámicamente, lo que activa una re-planificación.

# Linux

Esta en constante evolución, y cambiante de acuerdo a la versión del núcleo
- Linux almacena toda la información referida al proceso, incluyendo su planificación en su PCB. Estructura task_struct
- Características según la versión:
	- $0.96$: planificador bastante simple, buena respuesta a mucha E/S. Basado en prioridades dinámicas, con rodajas de tiempo y desalojo pero sin colas, el proceso se elegía a partir de un grupo de procesos listos.
	- $1.2$: Cada proceso almacena la política de planificación en su PCB. Si bien Linux no es un SO en tiempo real, a partir de esta versión se podía planificar un proceso como de tiempo real.
	- $2.2$: Clases de planificación y permite políticas de planificación para tareas de tiempo real y tareas no desalojables. También incluyó soporte para multiprocesamiento simétrico.

## Planificación en Linux: version 2.4

El planificador dividía el tiempo en períodos (*epochs*). Dentro de ese período, un proceso podía ejecutar hasta agotar su rodaja de tiempo.
- Si el número de procesos era grande, el planificador podía demandar una notable cantidad de tiempo de procesador.
- Carecía de prestaciones para aprovechar el multiprocesamiento simétrico
## Planificación en Linux: version 2.6.8.1

Uno de los cambios más significativos a partir de la serie 2.5 fue el cambio del
planificador. Uno de los grandes desafío fue disminuir el tiempo de cálculo que se incrementaba con la cantidad de proceso

Uno de los disparadores de este cambio fue el uso de Java, que a través de su
máquina virtual, los programas crean múltiples hilos de ejecución

Base funcional sustentada en 2 estructura:
- Cola de ejecución (_runqueue_)
- **Arreglos de Prioridad (140 niveles):** Cada cola tiene 2 arreglos (_Activo_ y _Expirado_). Cada arreglo posee 140 listas enlazadas (una por nivel de prioridad):
	- **0 a 99 (100 posiciones):** Reservadas para tareas de **tiempo real**.
	- **100 a 139 (40 posiciones):** Destinadas a tareas normales o de **usuario**.
**Dinámica de Ejecución:**
- El planificador toma la primera tarea del arreglo **Activo** siguiendo un orden FIFO en cada nivel de prioridad.
- Cuando una tarea consume su rodaja de tiempo (_timeslice_), se le recalcula una nueva prioridad y rodaja, y pasa al arreglo **Expirado**.
- **Intercambio de arreglos:** Al quedarse vacío el arreglo activo, los arreglos _Activo_ y _Expirado_ simplemente se intercambian mediante punteros.

Utiliza la instrucción de hardware `find-first-bit-set` sobre un mapa de bits para hallar al instante la mayor prioridad que tiene tareas listas. 

> [!note] El tiempo para elegir la siguiente tarea **siempre es constante** y depende únicamente del número de prioridades (140), no del número de tareas en el sistema.
## Planificación en versiones posteriores de Linux

- 2.6.21:
	- Más versatilidad en la configuración de la frequencia de interrupciones.
	- Mayor interactividad.
	- Más sobrecarga incluso en momentos de inactividad (muchas interrupciones para atender)
- 2.6.23
	- **CFS (completely Fair Scheduler)**.
	- CFS modela básicamente a una CPU multitarea ideal y precisa sobre hardware real.
	- Tiempo de ejecución virtual.
	- El tiempo de espera de una tarea es el que se considera que la tarea hubiera merecido en el modelo de equidad.
	- CFS no usa rodajas de tiempo en el sentido convencional, sino que calcula rodajas de tiempo para cada proceso justo antes de ser planificado.

