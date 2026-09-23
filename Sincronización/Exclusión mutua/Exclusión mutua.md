## Soluciones de hardware

- Inhabilitación de las interrupciones. (evitar la ejecución de rutinas de servicio)
- Instrucciones especiales de máquina.
	- TSL (test and set lock) Cerrojo exclusivo al hilo invocador, ningún otro hilo tendrá acceso
	- CAS (compare and swap) La operación falla si el valor fue alterado por otro hilo)
	- Fetch-and-add (trae y suma en una única operación)
	- Read-modify-write (idem anteriores, operación atómica)
	- Load-link/store-conditional

## Soluciones de software

- [[Algoritmo de Dekker]].
- [[Algoritmo de Peterson]].
Requisitos de una solución:

- **Exclusión mutua:** Solo un hilo podrá estar ejecutando en la sección crítica
- **Progreso:** Se elige entre los hilos que están interesados en acceder a la sección crítica.
- **Espera limitada:** Límite en la cantidad de intentos que hace un hilo para entrar en su sección crítica hasta que finalmente logra hacerlo.