Si el sistema operativo conoce el conjunto de trabajo al momento de que el proceso
fue intercambiado a almacenamiento secundario, puede prepaginar (prepage) todas
las páginas en ese conjunto de trabajo cuando el proceso sea intercambiado
nuevamente a memoria.

El prepaginado previene que la referencia inicial a las páginas del conjunto de trabajo generen un fallo de página. Esto le ahorra al SO la sobrecarga extra de procesar esos fallos de página. Sin embargo, algunas de las páginas cargadas pueden nunca ser referenciadas. Prepaginar una pagina que no es referenciada, degrada el rendimiento de la entrada/salida y desperdicia marcos de página.