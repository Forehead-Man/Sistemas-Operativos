El algoritmo de Dekker es un algoritmo de programación concurrente para [[Exclusión mutua]], que permite a dos procesos o hilos de ejecución compartir un recurso sin conflictos. Fue uno de los primeros algoritmos de exclusión mutua inventados, implementado por Edsger Dijkstra.

> [!note] Si ambos procesos intentan acceder a la sección crítica simultáneamente, el algoritmo elige un proceso según una variable de turno. Si el otro proceso está ejecutando en su sección crítica, deberá esperar su finalización.
## Condiciones

- No hay prioridad entre procesos.
- La capacidad de los equipos es irrelevante.
- Si un proceso muere fuera de la región crítica, el algoritmo sigue funcionando.
- Un bloqueo mutuo no se considera como solución válida.
