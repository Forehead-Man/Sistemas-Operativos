Para llevar a cabo tareas de colaboración y competencia por los recursos de hardware, el sistema operativo provee mecanismos de **comunicación y sincronización** entre [[Proceso|procesos]].

## Clasificación de Procesos según su Interacción

* **Proceso Independiente:** No afecta ni puede ser afectado por la ejecución de otros procesos en el sistema.
* **Proceso Cooperativo:** Puede afectar o ser afectado por la ejecución de otros procesos que corren en el sistema.

## Concurrencia y Sincronización

* **Procesos Concurrentes:** Dos procesos son concurrentes cuando la primera instrucción de uno se ejecuta después de la primera instrucción del otro y antes de la última (hay solapamiento temporal en la ejecución).
* **Necesidad de Sincronización:** Cuando los procesos se juntan o concurren en el mismo espacio y tiempo para acceder a los mismos recursos, es obligatorio establecer mecanismos de sincronización para evitar condiciones de carrera.

---
## Sub-notas del Tema

* **[[Procesos Concurrentes]]**: Conceptos de orden de ejecución, indeterminismo y comportamiento de sistemas concurrentes.
* **[[Mecanismos de IPC]]**: Paradigmas principales (memoria compartida y pase de mensajes) y mecanismos provistos por el SO (sockets, tuberías, señales, etc.).