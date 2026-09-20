El administrador de memoria de un sistema operativo debería cumplir con las siguientes funciones:
- **Reubicación:** Sistema de [[memoria virtual]].
- **Protección:** Los [[Proceso|procesos]] no deben ser capaces de acceder al espacio de memoria de otros procesos.
- **Compartimiento:** Hay casos donde si se desea compartir memoria entre procesos sobre todo en los mecanismos de comunicación.
- **Organización lógica:** Organización que surge en cómo están estructurados internamente los procesos. Un ejemplo es la [[Segmentación Simple|segmentación]]
- **Organización física:** 2 niveles: memoria principal (rápida en el orden de los nanosegundos) y secundaria (más lenta, en el orden de los milisegundos). El gestor de memoria del SO se encarga de mover los datos de una a otra.