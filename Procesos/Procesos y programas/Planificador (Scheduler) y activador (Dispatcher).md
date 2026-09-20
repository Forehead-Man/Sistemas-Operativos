### Planificador (Scheduler)

El **planificador (scheduler)** es un código que forma parte del [[Núcleo (Kernel)|núcleo del sistema operativo]].
- Entra en ejecución cada vez que se activa el sistema operativo y su misión es seleccionar el proceso que se ha de ejecutar a continuación.

#### **Fases de la planificación:**
- **Planificación a largo plazo:** determina qué trabajos o [[Proceso|procesos]] pueden competir por los recursos del sistema. Provee al de mediano de un apropiado número de trabajos.
- El **planificador de mediano plazo** o intercambiador (swapper) intercambia procesos entre la memoria RAM y un [[Memoria virtual|espacio en disco]].
- El **planificador de corto plazo** selecciona el proceso que será asignado a la CPU y el activador es el que efectivamente carga el proceso en la CPU y es también el que se encarga de pasar a [[modo usuario]]

### Activador (Dispatcher)

El **activador (dispatcher)** también forma parte del sistema operativo y su función es poner en ejecución el proceso seleccionado por el planificador.