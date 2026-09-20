**Definición:** Número entero no negativo que utiliza el sistema operativo para identificar de forma única un archivo o canal de comunicación abierto por un proceso.
- **Canales estándar (Fijos por defecto):**
    - **`0` (`stdin`):** Entrada estándar.
    - **`1` (`stdout`):** Salida estándar.
    - **`2` (`stderr`):** Error estándar.

Cuando se abre un nuevo archivo mediante la llamada al sistema `open` o `openat`, el núcleo le asigna el primer entero disponible (usualmente el `3`).
- Las llamadas como `read(3, ...)` o `close(3)` operan directamente sobre este descriptor.