### Partición absoluta única

El espacio de memoria está dividido en dos: una para el SO y la otra para UN proceso en ejecución. Supone buen comportamiento. Los primeros DOS usaban una variante de este.

Cuando un programa se carga, las direcciones deben corresponder con las direcciones en la partición. Pueden estar limitadas a direcciones de memoria en particular durante la compilación: **código absoluto**.

Si el binding ocurre durante la carga es **código reubicable** se le puede agregar protección agregándole al hardware un registro base. El SO carga el RB con la dirección más baja accesible por un proceso, luego compara cada dirección generada por el proceso con el contenido del RB y las menores provocan un fallo.

![[Partición absoluta unica.png]]
### Partición reubicable única

Contiene un [[Registros del Procesador|registro]] de reubicación. Es cargado por el SO con la dirección de comienzo del proceso. Pero en lugar de comparar, sus contenidos se suman. Se opera en un espacio de direcciones lógico.
- Es compilado como si fuera a ser asignado a la memoria que comienza en la ubicación 0.
- El hardware de administración de memoria convierte las direcciones lógicas en las direcciones físicas verdaderas.

**"Única":** La memoria RAM disponible para los usuarios se trata como un **bloque continuo y único**. Solo hay **un único proceso de usuario** cargado en memoria ejecutándose a la vez (junto con el espacio reservado para el Sistema Operativo).

**"Reubicable":** Gracias al uso de hardware específico (como un **registro de reubicación** o registro base), el programa no necesita estar compilado para ejecutarse en una dirección física fija de la memoria. El sistema operativo puede cargar ese único proceso en distintas direcciones de la RAM cada vez que se ejecuta.


### Superposiciones - Overlays

En los sistemas de monoprogramación antiguos (o en sistemas embebidos/SoC actuales que carecen de memoria virtual), un programa solo podía ejecutarse si entraba por completo en la memoria física disponible. Si el programa era más grande que la RAM, no se podía ejecutar.

**División en partes independientes:** El programa se divide manualmente en bloques llamados **superposiciones (_overlays_)**. Solo se cargan en la RAM las partes que se necesitan ejecutar en un momento determinado.

**Reutilización del mismo espacio de memoria:** Cuando termina una fase del programa, se descarga de la RAM y se sobrescribe (_superpone_) la siguiente parte en ese mismo sector de memoria.

![[Overlays.png]]
La tabla muestra un ensamblador de dos pasadas que ocupa **200 KB en total**:
- **Código del paso 1:** 70 KB
- **Código del paso 2:** 80 KB
- **Tabla de símbolos:** 20 KB
- **Rutinas comunes a ambos pasos:** 30 KB

Si solo tuvieras **130 KB de RAM**, no podrías cargar los 200 KB al mismo tiempo. Con _overlays_ se organiza así:
- **Superposición A (para la Pasada 1):** Carga en memoria la tabla de símbolos (20 KB) + rutinas comunes (30 KB) + código del paso 1 (70 KB) = **120 KB total**.
- **Superposición B (para la Pasada 2):** Cuando termina el paso 1, se sobreescribe el código del paso 1 cargando el código del paso 2 (80 KB) sobre el mismo espacio de RAM. Ahora se usa la tabla de símbolos (20 KB) + rutinas comunes (30 KB) + código del paso 2 (80 KB) = **130 KB total**.

De esta manera, un programa de 200 KB puede correr en solo 130 KB de memoria física.

