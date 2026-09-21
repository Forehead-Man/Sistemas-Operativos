ELF (Executable and Linkable Format) organiza código, datos, símbolos, reubicaciones y bibliotecas para que el enlazador y el núcleo puedan usar un objeto. 

Para ubicar los tres tipos principales en la ruta del programa, sigamos el caso de hello.c:
1. **Archivo reubicable (relocatable file).** Contiene código y datos to davía enlazables con otros objetos. Es la salida de compilar con `gcc -c hello.c`; en Linux suele tener extensión .o (y .ko en un módulo del núcleo), y todavía no está listo para iniciar.
2. **Archivo ejecutable (executable file)**. Es el resultado usual de enlazar objetos y bibliotecas; queda listo para iniciar. Un script de shell no es un ELF: quien se ejecuta es su intérprete. En Linux suele no llevar extensión, como el ejecutable hello.
3. **Objeto compartido (shared object).** Es una biblioteca que puede enlazarse o cargarse junto con un programa; en Linux suele tener extensión .so. No es un paso obligatorio después del ejecutable, sino una rama paralela que puede participar en el enlace o en la carga. 

El recorrido principal del practico es `hello.c → hello.o → hello → proceso`.