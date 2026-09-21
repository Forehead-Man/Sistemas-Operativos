Formado por varias regiones o segmentos creadas a partir de la info del
ejecutable en tiempo de ejecución.

Cada región es una zona contigua y con las siguientes características:
- **Soporte de la región** (donde está almacenada la región)
	- Soporte en archivo
	- Sin soporte. No tiene contenido inicial
- **Tipo de uso compartido**
	- Privado. Solo accesible por ese [[Proceso]].
	- Compartido. El cont. de la región es accesible por otros procesos.
- **Protección**
	- Lectura
	- Ejecución
	- Escritura
- **Tamaño fijo o variable.**
- **Código (texto):** Región compartida. Tamaño fijo. Está en el ejecutable - .text
- **Datos con valor inicial:** Región privada. Tamaño fijo. Con soporte en el ejecutable (int i=7). Es .data
- **Datos sin valor inicial:** Región privada. RW y tamaño fijo indicado en la cabecera del ejecutable. Ej int i[10]. Es .bss
- **Pila o stack:** Región privada. Almacena registros de activación de las llamadas a funciones. Tamaño variable.
![[Mapa de memoria de un proceso.png]]

Los SO modernos ofrecen un modelo de memoria dinámico. El mapa está formado por un número variable de regiones. Pueden crearse estas:
- **Montículo o heap:** Memoria dinámica que reserva un proceso (malloc). Región privada. Comienza luego de la región de datos sin valor inicial.
- **Archivos proyectados:** Cuando se proyecta un archivo, se crea una región asociada al mismo.
- **Memoria compartida:** Cuando se crea una zona de memoria compartida y se proyecta, se crea una región asociada.
- **Pilas de threads:** cada thread necesita una pila propia que se corresponde con una nueva región en el mapa. Estructura LIFO.