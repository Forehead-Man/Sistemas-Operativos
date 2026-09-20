Como parte final del proceso de [[Generación de un ejecutable|compilación y enlace]] se genera un archivo ejecutable que contiene el código de máquina del programa. Un ejecutable está compuesto por una cabecera y un conjunto de secciones.
- **Cabecera:** Información de control.
- **Secciones:**
	- Código
	- Datos con valor inicial
	- Datos sin valor inicial (descrito en la cabecera pero no almacenado en el ejecutable porque no tienen valor)
![[Formatos de un ejecutable.png]]

### Formato ELF (Executable and Linkable Format)

Lo usan archivos objeto, ejecutables, bibliotecas compartidas y volcados de memoria. No está limitado a un procesador o arquitectura. Lo utiliza Unix/Linux, Playstation Portable, Playstation 2, Playstation 3 y Wii.

![[Formato ELF.png]]

### Formato PE

Parte de la especificación original Win32.
- Se utilizaba en VAX/VMS.
- Se lo usa en ejecutables y DLLs

A diferencia de ELF, que usa código independiente de la posición, PE se compila a una dirección base preferida y si no puede ser cargado en esa dirección preferida, el sistema operativo tiene que re-calcular la base.
![[Formato PE.png]]