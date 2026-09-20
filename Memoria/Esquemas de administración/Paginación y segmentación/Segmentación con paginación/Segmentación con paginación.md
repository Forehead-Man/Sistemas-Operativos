Esquema **híbrido** de administración de memoria que combina la organización lógica, protección y facilidad para compartir datos de la **segmentación** con la eficiencia de gestión física y ausencia de fragmentación externa de la **paginación**.

- **Estructura lógica:** El programa se divide en **segmentos** según su función (código, datos, pila).
- **Estructura física:** Cada segmento no se guarda de forma contigua, sino que internamente se **divide en páginas** de tamaño fijo asignadas a marcos de RAM.
- **Dirección lógica dividida en 3 partes:**
    1. **$s$ (Número de segmento)**: Identifica el módulo lógico del programa.
    2. **$p$ (Número de página)**: Identifica la página dentro de ese segmento.
    3. **$d$ (Desplazamiento / Offset):** Indica la posición exacta dentro de la página.

### Funcionamiento y traducción de direcciones

1. **(Buscar la Tabla de Páginas):** Se usa el número de segmento ($s$) como índice en la **Tabla de Segmentos**. La entrada obtenida contiene la dirección de inicio de la **Tabla de Páginas de ese segmento específico**.
2. **(Buscar el Marco Físico):** Se suma el número de página ($p$) a la dirección obtenida en el paso 1 para buscar en la **Tabla de Páginas** y extraer el número de marco físico ($pf$).
3. **(Formar la Dirección Física):** Se combina el marco físico ($pf$) encontrado con el desplazamiento original ($d$) para acceder a la celda de la RAM.

![[Segmentación con paginación.png|526]]