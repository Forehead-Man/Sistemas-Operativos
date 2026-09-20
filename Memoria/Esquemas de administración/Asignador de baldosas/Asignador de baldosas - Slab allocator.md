Dentro del núcleo se asigna una considerable cantidad de memoria para un
conjunto finito de descriptores de archivo y estructuras comunes.

Bonwick (1994) observó que la cantidad de tiempo requerido para inicializar un objeto ordinario excede la cantidad de tiempo requerido para asignarlo y
liberarlo. En lugar de retornar la memoria liberada al contenedor global, la memoria sigue inicializada para el propósito previsto, reteniendo su estado entre usos. 

Se elimina así la fragmentación provocada por la asignación y liberación de
memoria

El sistema operativo tiene "bandejas" creadas de antemano para las cosas pequeñas que usa todo el tiempo (como la lista de programas abiertos o los permisos de los archivos).

Cuando necesita guardar un dato nuevo de ese tipo, no pierde tiempo pidiendo y organizando espacio nuevo en la RAM: **usa directamente una forma que ya está lista en la bandeja**. Y cuando termina de usarlo, en lugar de tirar la bandeja, la limpia y la deja lista para la próxima.

> Utilizado por Linux hasta la version de kernel 2.6.23