First-Come-First-Serve. Primero en llegar, primero en ser atendido.

- Simple de implementar, se le asigna CPU al primero que lo solicita a medida que los proceso o hilos van arribando.
- Se organiza mediante una cola **FIFO (First In, First Out)**, colocando el [[PCB (Process Control Block)|PCB]] del proceso entrante al final de la cola
- Se elige el primero de esa cola para asignar CPU, y se lo ejecuta hasta que finalice. Algoritmo sin expulsión
- Poco eficiente, largos tiempos de espera.
- Procesos cortos pueden quedar atascados atrás de procesos más largos.