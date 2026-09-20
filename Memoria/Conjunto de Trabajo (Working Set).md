El **Conjunto de Trabajo** es un modelo diseñado para aproximar y medir cuántas y cuáles páginas de memoria RAM **necesita realmente un proceso en un momento específico** para ejecutarse eficientemente sin generar un exceso de fallos de página (evitando el colapso por hiperpaginación o _thrashing_).

Se basa directamente en el **principio de localidad de referencia** (los programas tienden a acceder a un conjunto concentrado de páginas durante una fase de su ejecución).

Se define como el conjunto de páginas a las que el proceso hizo referencia durante una **ventana de tiempo pasada** (Δ). Su notación matemática es: $W(t,Δ)$

- **$W$ (_Working Set_):** El conjunto de páginas resultantes.
- **$t$:** El instante de tiempo actual (que en la práctica suele medirse en **cantidad de instrucciones ejecutadas**).
- **$Δ$ (Delta):** La **ventana de tiempo o tamaño del intervalo** de observación. Representa el número total de referencias a memoria pasadas que se van a examinar para calcular el conjunto.

El éxito del modelo depende totalmente de seleccionar un valor adecuado para la ventana $Δ$:
- **Si $Δ$  es muy pequeño:** El intervalo no logrará abarcar todas las páginas activas de la fase actual del programa. El sistema operativo asumirá que el proceso necesita menos memoria de la real, lo que provocará **múltiples fallos de página**.
- **Si $Δ$ es muy grande:** El intervalo abarcará páginas viejas que el proceso utilizó en etapas anteriores pero que **ya no necesita**. Esto provocará un **desperdicio de memoria RAM**, impidiendo que otros procesos puedan utilizarla.

El sistema operativo utiliza el modelo del conjunto de trabajo para la **asignación dinámica de marcos de página**:

1. **Evitar la hiperpaginación (_thrashing_):** Si la suma de los tamaños de los conjuntos de trabajo de todos los procesos activos supera la cantidad total de RAM física disponible ($∑Wi​>RAM$), el SO suspende temporalmente uno o más procesos (los manda al disco / _swap-out_) para garantizar que los procesos restantes tengan su $W(t,Δ)$ completo en la RAM.
2. **Asignación eficiente:** Le otorga a cada proceso la cantidad exacta de marcos que necesita en cada fase de su ejecución, ajustando el espacio a medida que el programa cambia de función o módulo.