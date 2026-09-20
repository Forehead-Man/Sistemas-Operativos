Para permitir la multiprogramación, la protección entre **[[Proceso|procesos]]** y el uso eficiente de la **[[Memoria Principal]]**, los Sistemas Operativos diferencian distintos tipos de direcciones según su nivel de abstracción.

## 1. Dirección Física (Physical Address)

- **Definición:** Es la ubicación real, tangencial y concreta de una celda de datos dentro de los módulos de la **[[Memoria Principal]]** (RAM).
- **Características:**
    - Es la dirección que viaja a través del bus de direcciones del **[[Hardware]]**.
    - El proceso en **[[Modo Usuario]]** nunca ve ni manipula directamente estas direcciones; son gestionadas por el **[[Núcleo (Kernel)]]** y la unidad de gestión de memoria (MMU).
## 2. Dirección Lógica o Virtual (Logical / Virtual Address)

- **Definición:** Es la dirección generada por la **[[CPU]]** mientras ejecuta las instrucciones de un **[[Proceso]]**.
- **Características:**
    - Da a cada proceso la ilusión de tener su propio espacio de memoria continuo, aislado y privado.
    - Permite la protección de memoria: un proceso no puede acceder al espacio de dirección lógica de otro proceso.
    - La **MMU** (Memory Management Unit) es la encargada de traducir en tiempo de ejecución la _dirección lógica_ a su correspondiente _dirección física_.

## 3. Dirección Relativa o Relativa a Registro (Relative / Offset Address)

- **Definición:** Es un tipo de dirección lógica expuesta como un desplazamiento (_offset_) respecto a una posición de referencia inicial (generalmente un registro base).

- **Mecanismo:**

<center>Dirección Física = Registro Base + Dirección Relativa</center>

- **Uso:** Permite la **relocalización dinámica** de los programas en memoria, posibilitando que un proceso se cargue en cualquier región libre de la RAM sin necesidad de recompilar el código.

## 4. Dirección Absoluta / Lineal (Absolute Address)

- **Definición:** Es una dirección de memoria interreferenciada explícitamente en el código binario o máquina.

- **Características:**
    - En sistemas antiguos sin memoria virtual (como en las primeras **[[Arquitectura Von Neumann|Arquitecturas Von Neumann]]** o procesadores en modo real), las direcciones del programa coincidían directamente con las posiciones físicas de la memoria.
    - En sistemas modernos con paginación, la _dirección lineal_ es el resultado intermedio tras aplicar la segmentación antes de ser traducida por la tabla de páginas a dirección física.