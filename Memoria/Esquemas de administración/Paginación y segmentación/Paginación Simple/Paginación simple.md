Técnica de administración de memoria que elimina la **fragmentación externa** al permitir que el espacio de direcciones de un proceso se almacene de forma **no contigua** en la RAM.

- **Marcos de página (_page frames_):** División de la memoria física (RAM) en bloques del mismo tamaño fijo.
- **Páginas (_pages_):** División del proceso en bloques lógicos del mismo tamaño que los marcos.
- **Tabla de páginas:** Estructura que mantiene el sistema operativo por cada proceso para mapear cada **página lógica** con su **marco físico** correspondiente.

1. **Asignación no contigua:** Al cargar un proceso, el SO asigna sus páginas a marcos libres en la RAM, sin importar si están separados.
2. **Traducción de direcciones:**
	- La dirección lógica generada por la CPU se compone de un número de página ($p$) y un desplazamiento ($d$).
	- Se busca $p$ en la **Tabla de Páginas** para obtener el marco físico ($pf$).
	- La dirección física final se forma uniendo el marco ($pf$) con el desplazamiento ($d$).

![[Paginacion simple.png|366]]

A diferencia del **particionamiento fijo** tradicional, la paginación maneja bloques mucho más pequeños, permite que un proceso ocupe múltiples bloques y elimina la necesidad de que estén pegados unos a otros en la RAM.

