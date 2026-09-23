El término se refiere a las relaciones entre fenómenos o eventos – cualquier
número de eventos y cualquier clase de relación, tal como antes, durante o después.

- El evento A debe ocurrir antes que el evento B o, los eventos A y B no deben ocurrir a la vez.
- Normalmente se necesita de un reloj para forzar la sincronización pero no siempre es posible. Por eso, nos valemos de técnicas en software para lograrlo.
- Si tuviéramos una computadora capaz de cargar un único programa y ejecutarlo de principio a fin, no tendríamos necesidad de sincronización. Por eso, estas técnicas le darán a nuestros procesos esa ilusión

### Condición de carrera

Una situación en la que varios procesos o hilos acceden a, y manipulan, los mismos datos de forma concurrente, y el resultado de la ejecución depende del orden en que haya ocurrido el acceso, se denomina condición de carrera (o competencia) (a.k.a race condition).

### Sección critica

Si dos hilos necesitan incrementar la misma variable global, cada uno
de ellos deberá asegurar que tiene acceso exclusivo a esta variable durante algún
período de tiempo.

Denominaremos **sección crítica** al segmento de código en el cual un hilo está
accediendo en exclusividad a un recurso compartido (una variable, una estructura
de datos, un dispositivo) y que no debe ser accedido concurrentemente por otro.

La ejecución de secciones críticas de los procesos o hilos es mutuamente excluyente
en el tiempo.


[[Exclusión mutua|¿Como se logra la exclusión mutua?]]