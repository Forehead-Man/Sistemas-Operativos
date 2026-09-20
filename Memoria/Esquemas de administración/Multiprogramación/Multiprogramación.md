En un ambiente de multiprogramación hay **varios procesos compartiendo la memoria**. El SO divide la memoria en varias particiones para que múltiples procesos queden residentes.

### Múltiples particiones fijas

Si todas las particiones son del mismo tamaño, el SO sólo necesita llevar la cuenta de cuáles particiones están asignadas a cada proceso. La tabla de particiones de memoria almacena o bien la dirección de comienzo para cada proceso o el número de la partición asignada. El espacio al final de una partición que no es usado, se desperdicia, esto genera algo llamado **fragmentación interna.**

![[Pasted image 20260920155737.png]]

### Múltiples particiones variables

Para solucionar el desperdicio del esquema fijo, surgen las particiones variables. Aquí la memoria no se divide de antemano; en su lugar, se asigna a cada proceso **exactamente la cantidad de memoria que solicita** en el momento de cargarse.

A medida que los procesos se van creando y terminando, el uso de la
memoria evoluciona hacia secciones alternadas de espacio asignado y sin
asignar. Empiezan a generarse huecos de memoria. A este espacio desperdiciado no asignado a ninguna partición se le llama **fragmentación externa**.

Se puede emplear **compactación** para hacer un uso más eficiente de la
memoria aunque este movimiento puede implicar una sobrecarga.

![[Fragmentación externa y compactación.png]]