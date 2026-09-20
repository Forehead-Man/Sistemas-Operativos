---
padre: "[[Hilos (Threads)]]"
---
## 1. Diseños y Primitivas del Sistema

Un sistema que da soporte a hilos debe proveer un conjunto de primitivas o paquete de funciones:

- **Creación:** De forma estática o dinámica.
- **Terminación:** Similar a los procesos, cuando finaliza su trabajo o al recibir una señal externa.
- **Sincronización:** Mecanismos para prevenir accesos simultáneos conflictivos a los recursos compartidos.
- **Planificación:** 
	- Asignación de prioridades.
	- Variación dinámica del *quantum*.
	- Planificación forzada o por prioridad.
- **Manejo de Señales:** Las señales proveen **[[Interrupciones]]** generadas por software y excepciones:
	- **Interrupciones:** Disrupciones generadas externamente a un hilo/proceso.
	- **Excepciones:** Causadas por condiciones inusuales durante la ejecución interna del propio hilo.


## 2. Modelos de Organización de Hilos

Existen tres patrones principales de arquitectura para organizar la interacción de hilos dentro de un proceso:

### A. Modelo Despachador-Trabajadores (Dispatcher-Worker)
* **Funcionamiento:** Un único **hilo despachador** acepta las solicitudes de los clientes, las examina y las despacha a uno de los **hilos trabajadores** que esté libre para su procesamiento.
![[Modelo Despachador-Trabajador.png]]

### B. Modelo Pipeline (Tubería)
* **Funcionamiento:** Útil para aplicaciones basadas en el modelo **Productor-Consumidor**. Los datos de salida generados por un hilo se utilizan directamente como la entrada de otro hilo en secuencia.
![[Modelo Pipeline.png]]
### C. Modelo Equipo (Team)
* **Funcionamiento:** Todos los hilos se comportan como iguales (sin jerarquía). Cada hilo obtiene y procesa solicitudes por sí mismo. Se utiliza para la implementación de hilos especializados dentro de un mismo proceso.
![[Modelo Equipo.png]]