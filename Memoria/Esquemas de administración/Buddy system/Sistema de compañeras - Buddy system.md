Es un compromiso entre la asignación de tamaño fijo y variable.
- La memoria se asigna en unidades que son potencia de 2.
- A un proceso se le asigna una unidad cuyo tamaño es la menor potencia de 2 pero mayor o igual que el tamaño del proceso. Ejemplo: a un proceso de 50K se lo ubicará en una de 64K.

Si no existe una de 64K, la asignación disponible más chica mayor que el proceso se dividirá en dos unidades “compañeras” de la mitad del tamaño que la original. La división continúa con una de las unidades compañeras hasta que se crea una unidad de asignación del tamaño apropiado.

Cuando un proceso libera memoria provoca que se liberen dos unidades compañeras, las unidades se combinan para formar una unidad dos veces más grande, tratando de ese modo de minimizar la fragmentación.

![[Buddy system.png]]