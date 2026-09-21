Asocia un valor a cada proceso que representará su prioridad y se le asigna la CPU al proceso de la cola de listos que tenga el mayor valor.
- Según el SO el valor puede estar en un rango fijo de $0-n$.
- Cada sistema también determina cual es el número con mayor o menor prioridad
- La prioridad puede ser fija o variable. Si es variable, puede cambiar durante la vida del proceso.
	- Prioridad Interna: el sistema decide de acuerdo a factores medibles y en función del uso de los recursos como memoria, archivos abiertos y tiempos de E/S
	- Prioridad Externa: interviene el operador. O factor económico, donde se paga por el procesamiento.