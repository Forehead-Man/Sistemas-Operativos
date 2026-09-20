**Distinción crítica:**

- El usuario **`root`** (representado con el prompt `#` en la terminal) es una cuenta del **[[Sistema Operativo]]** con privilegios administrativos de software.
- Estar como `root` **no significa que los procesos se ejecuten en Ring 0 o [[Modo Núcleo]]**.
- Los **[[Anillos de Protección]]** (Ring 0 / Ring 3) son niveles de privilegio del **[[Hardware]]** de la CPU, mientras que `root` es solo una identidad dentro del control de acceso del sistema operativo.