Mecanismo que combina la **paginación simple** con la filosofía de las **[[Monoprogramación|superposiciones (overlays)]]** para implementar **[[Memoria virtual]]**. En lugar de cargar todo el programa en la RAM desde el principio, una página solo se trae a la memoria física **cuando el proceso intenta acceder a ella** ("perezoso" o _lazy loading_).

- **Almacenamiento secundario:** Todas las páginas del proceso se guardan originalmente de forma continua en el espacio de intercambio (_swap_) o archivo en disco.
- **Bit de presencia (_in/out bit_ o _present/valid bit_):** Indicador en la tabla de páginas que señala si una página está cargada en la RAM (`1`/`in`) o permanece en el disco (`0`/`out`).
- **Fallo de página (_Page Fault_):** Excepción o trampa (_trap_) que genera la MMU cuando el proceso intenta acceder a una página que tiene el bit de presencia desmarcado (`0`/`out`).
## Funcionamiento paso a paso

1. **Consulta:** Al generar una dirección virtual, la MMU extrae el número de página y busca su entrada en la tabla de páginas.
2. **Verificación del bit de presencia:**
    - **Página en RAM (`in`):** Se extrae el marco físico, se suma el desplazamiento y se accede a la memoria (funciona como paginación simple).
    - **Página en Disco (`out`):** Se interrumpe la ejecución y se activa la rutina de fallo de página del SO.
3. **Manejo del Fallo de Página:** El sistema operativo busca la página solicitada en el disco, localiza un marco libre en la RAM, la carga, actualiza la tabla de páginas con el marco asignado (cambiando el bit a `in`) y reanuda la instrucción interrumpida.

## Detalles de implementación y optimización

- **Escritura selectiva (_Dirty Bit_):** Al reemplazar o sacar una página de la RAM, solo aquellas páginas que **fueron modificadas** durante su estancia en memoria necesitan ser reescritas en el disco (_swap-out_). Si no cambiaron, simplemente se des-asignan para ahorrar E/S.
- **Direccionamiento con/sin Memoria Virtual:**
    - _Sin memoria virtual:_ La dirección del proceso se coloca directamente en el bus de memoria física.
    - _Con memoria virtual:_ Toda dirección pasa obligatoriamente por la MMU para su traducción.
- **Paginación por Demanda Pura:** El proceso arranca con cero páginas en RAM. Al inicio genera una serie continua de fallos de página desde la primera instrucción hasta que carga el conjunto de páginas mínimo necesario (_working set_) y el rendimiento se estabiliza.