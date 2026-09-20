---
padre: "[[Comunicación e IPC (Inter-Process Communication)]]"
---
## 1. Definición de Concurrencia
Dos eventos o instrucciones son **concurrentes** si, mediante la sola observación del programa, **no podemos establecer cuál ocurrirá primero**.
## 2. Características de la Ejecución Concurrente

A diferencia de los programas secuenciales, la ejecución de sistemas concurrentes presenta particularidades clave:

- **Orden Total vs. Orden Parcial:**
	- **Programas Secuenciales:** Existe un *orden total* en la ejecución de las líneas de código. Dado un conjunto de datos de entrada, se conoce de antemano la secuencia exacta de pasos.
	- **Programas Concurrentes:** Existe un *orden parcial*. Ante el mismo conjunto de datos de entrada, no es posible determinar con certeza cuál será el flujo exacto de ejecución en cada corrida.

- **Indeterminismo:**
	- El orden parcial puede llevar a que un programa concurrente tenga un **comportamiento indeterminado**, es decir, arrojar resultados diferentes al ejecutarse repetidamente con los mismos datos de entrada si no existe una correcta sincronización.
## 3. Ejecución en Multiprocesamiento
Si se dispone de múltiples procesadores o núcleos en la CPU, las instrucciones que no guardan dependencia de orden entre sí se pueden ejecutar en paralelo, incrementando sustancialmente la velocidad y rendimiento del sistema.