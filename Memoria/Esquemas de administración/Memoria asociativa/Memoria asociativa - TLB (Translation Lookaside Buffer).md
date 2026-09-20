La **TLB** es una memoria **caché especial ultrarrápida** integrada dentro del procesador y gestionada por la MMU (_Memory Management Unit_). Su objetivo es acelerar la traducción de [[Dirección de Memoria|direcciones lógicas a físicas]] en sistemas con paginación, evitando consultar la RAM para leer la tabla de páginas en cada acceso a memoria.

- **Direccionamiento por contenido:** A diferencia de la RAM tradicional (que busca por dirección o índice), la memoria asociativa compara el número de página ($p$) con **todas sus entradas en paralelo al mismo tiempo**.
- **Nombre "_Lookaside_" ("Mirar de reojo"):** Se llama así porque el hardware busca en la TLB en paralelo al intento de acceso a la tabla de páginas en RAM.
- **Acierto (_TLB Hit_):** La página buscada se encuentra guardada en la TLB.
- **Fallo (_TLB Miss_ / _Page Walk_):** La página no está en la TLB. Se debe ir a la RAM física a consultar la tabla de páginas, lo que consume varios ciclos de reloj adicionales.

## Funcionamiento paso a paso

1. **Búsqueda simultánea:** La CPU genera una dirección lógica compuesta por el número de página ($p$) y el desplazamiento ($d$). Se busca $p$ en la TLB.
2. **Evaluación:**
    - **Caso A — _TLB Hit_:** Si el número de página ($p$) está en la TLB, se cancela la búsqueda en la RAM y se extrae el marco físico ($pf$) directamente desde la TLB.
    - **Caso B — _TLB Miss_:** Si no está en la TLB, se recorre la tabla de páginas en la memoria RAM (_page walk_) para obtener el marco ($pf$). (Si la página tampoco está en la RAM, el SO genera una **falla de página**).
3. **Actualización:** Al ocurrir un fallo, la nueva traducción ($p→pf$) se guarda en la TLB para accesos futuros, reemplazando la entrada menos usada recientemente (política LRU).
4. **Acceso final:** Se combina el marco ($pf$) con el desplazamiento ($d$) para generar la dirección física final.

![[Memoria asociativa.png|421]]