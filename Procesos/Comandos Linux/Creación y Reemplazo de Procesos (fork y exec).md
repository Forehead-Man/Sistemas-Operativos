**`fork()`:** [[Llamada al sistema]] que crea un nuevo [[Proceso]] (hijo) que es una **copia exacta** del [[Proceso]] que lo invocó (padre).
    - **Valores de retorno para bifurcación:**
        - `< 0` (`-1`): Error en la creación del proceso.
        - `0`: Indica que se está ejecutando dentro del **proceso hijo**.
        - `> 0`: Se ejecuta dentro del **proceso padre** y el valor retornado es el [[Identificación y Relación Padre-Hijo|PID]] asignado al nuevo hijo.

**`exec()` (familia de funciones):** [[Llamada al sistema]] que **reemplaza el espacio de memoria y la imagen del [[Programa]] actual** por un nuevo ejecutable.

**Mecanismo del Shell:** Para ejecutar cualquier comando, la consola utiliza el patrón `fork()` (duplica el shell) y seguidamente el hijo invoca `exec()` para cargar y ejecutar el programa indicado.