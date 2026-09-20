**Definición:** Cada [[Proceso]] se representa en el [[sistema operativo]] mediante una
estructura de datos llamada bloque de control de procesos (PCB de
Process Control Block)

- **Estado del proceso:** nuevo, bloqueado, listo, etc. (ver [[Pasted image 20260916012401.png]])
- **[[Contador de programa]]:** indica la dirección de la siguiente instrucción que se ejecutará.
- **Registros de CPU:** el número y el tipo de los [[Registros del Procesador|registros]] (acumuladores, registros índice, punteros de pila, etc).
- **Información de planificación de CPU:** [[prioridad]] del proceso, punteros a colas de [[planificación]].
- **Información de gestión de memoria:** valor de los registros de base y de límite, tablas de páginas o tablas de segmentos.
- **Información contable:** cantidad de tiempo de CPU, tiempo consumido, límites de tiempo.
- **Información de estado de entrada o salida:** lista de dispositivos de [[Entrada y Salida (E-S)|entrada o salida]] asignados, lista de archivos abiertos, etc.