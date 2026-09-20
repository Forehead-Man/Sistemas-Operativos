Esquema de administración de memoria no contigua donde el programa se divide en bloques de **tamaño variable** llamados **segmentos**, organizados según la estructura lógica de la aplicación (código, datos, pila, etc.) y generados por el compilador.

A diferencia de la paginación, la memoria física **no se divide en marcos de tamaño fijo**.

- **Segmentos:** Módulos de tamaño variable (como una función, un arreglo o la pila). El compilador puede definir permisos específicos para cada uno (por ejemplo, de solo lectura o compartidos).
- **Tabla de segmentos:** Estructura que almacena para cada segmento dos datos fundamentales:
    - **Base (`ADDR`):** Dirección física donde inicia el segmento en la RAM.
    - **Límite (`LEN`):** Longitud o tamaño total del segmento.

La dirección lógica consta de un **número de segmento ($s / p$)** y un **desplazamiento ($d$)**:

1. **Búsqueda:** El número de segmento se usa como índice en la **Tabla de Segmentos** para obtener su base (`ADDR`) y su límite (`LEN`).
2. **Validación de seguridad:** Se verifica si el desplazamiento es válido ($d<LEN$).
    - **Si $d≥LEN$:** El acceso es ilegal y el hardware genera una **trampa/falla de dirección** (_segmentation fault_).
3. **Cálculo físico:** Si la dirección es válida, se calcula la dirección física sumando la base y el desplazamiento ($Dirección física = ADDR + d$).

