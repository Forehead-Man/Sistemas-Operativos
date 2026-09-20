---
padre: "[[Comunicación e IPC (Inter-Process Communication)]]"
---
La comunicación entre procesos (IPC) es una función básica de los sistemas operativos.
## Paradigmas Principales de IPC

Existen dos formas fundamentales de abordar la comunicación entre procesos:

1. **Memoria Compartida (Shared Memory):**
   * El sistema establece un área común de la **[[Memoria Principal]]** a la que varios procesos tienen acceso de lectura y escritura.
1. **Pase de Mensajes (Message Passing):**
   * Los procesos se comunican mediante el envío y recepción explícita de mensajes cifrados o estructurados gestionados por el **[[Núcleo (Kernel)]]**.
## Mecanismos Específicos de Comunicación

El sistema operativo proporciona diversos mecanismos o primitivas para implementar IPC:

* **Puertos:** Actúan como un buzón de entrada donde uno o más procesos depositan mensajes para un receptor.
* **Señales:** Versión limitada de IPC que consiste en notificaciones asíncronas enviadas a un proceso desde el SO o desde otro proceso. También se las conoce como **interrupciones por software**.
* **Temporizadores:** Tipo de interrupción de reloj que se configura para interrumpir al procesador cuando alcanza el valor cero.
* **Sockets:** Mecanismo de interfaz ("zócalo") que permite conectar dos procesos remotos a través de una red o de forma local.
* **Tuberías (Pipes):** Pseudo-archivo mantenido en memoria por el sistema operativo que sirve para conectar la salida de un proceso con la entrada de otro. (| en [[Linux]])
* **Cola de Mensajes:** Servicio provisto por el SO para almacenar mensajes en un buffer intermedio que luego son consumidos asíncronamente por otro proceso.
* **Archivos:** Dos o más procesos pueden intercambiar información leyendo y escribiendo en archivos del almacenamiento secundario.
* **Archivos Proyectados en Memoria (Memory-Mapped Files):** Asignación de un espacio de la **[[Memoria Principal]]** que se relaciona byte a byte con un archivo en disco. Las lecturas y escrituras en esa zona de memoria se tratan directamente como operaciones nativas sobre el archivo.
* **Excepciones:** Cuando un hilo o proceso realiza una operación no permitida (como división por cero), el hardware o el procesador genera una excepción que es capturada e interrumpida por el manejador de excepciones en el **[[Modo Núcleo]]**.